# Capacitors and AC Coupling

- capacitor
  - menstabilkan tegangan, menghilangkan noise
  - satuannya yaitu Farad (F)

### Fungsi Capacitor

    * Low Pass Filter: Meloloskan sinyal pelan (Bass), membuang sinyal cepat (Treble/Noise). Dipakai untuk membersihkan sinyal sensor yang jittery (gemetar). rangkaiannya resistor dulu baru capacitor (capacitor nempel ground).
    * High Pass Filter: Meloloskan sinyal cepat, memblokir sinyal diam (DC). Dipakai di audio amplifier agar tegangan baterai tidak masuk ke speaker. rangkaiannya capacitor dulu baru resistor. (resistor nempel ground)

### Series and Parallel Capacitor

- Parallel Capacitor
  - Ct = C1 + C2 + C3 + ...
- Series Capacitor
  - Ct = C1 \* C2 / (C1 + C2)
  - Capacitor disusun series sangat jarang sekali digunakan, mending langsung pasang capacitor yang besar

### Konsep RC Circuit

    * Konsep Rangkaian RC (Resistor + Capacitor) = TIMER
    * Ini adalah konsep paling vital untuk logika digital dan mikrokontroler.
    * Jika Anda menghubungkan Resistor dan Kapasitor secara seri (berurutan), listrik tidak akan langsung "penuh" tapi berangsur-angsur akan penuh (charging capacitor).
    * Kapasitor akan terisi secara perlahan mengikuti kurva melengkung.
    * Kapasitor dianggap penuh (charging) (100%) setelah (pada detik) 5 * R(Ohm) * C(Farad).
    * Jadi misal R = 100 Ohm, C = 100 uF, maka waktu tunda(timer) yang dihasilan yaitu 5 * 100 * 100 uF = 5000 uF = 5 ms.
    * Contoh:Anda menekan saklar. Lampu tidak langsung nyala terang, tapi redup dulu baru terang (charging) perlahan. Itu efek rangkaian RC. Saat sumber tegangan dicabut maka lampu tidak langsung mati tapi meredup dulu baru mati (discharging) perlahan.
    * __5 * R * C__ itu adalah waktu tunda untuk __charging__ sampai penuh dan waktu tunda untuk __discharging__ sampai habis.

### Implementasi dari Low Pass Filter

    * Bypass / Decoupling Capacitor
        * Fungsi: Menstabilkan tegangan suplai ke chip.
        * Lokasi Pasang: Di kaki VCC.
        * Kapan Berfungsi: Terus-menerus selama alat menyala.
        * Masalah: Chip digital (seperti ESP32) bekerja dengan kecepatan sangat tinggi. Ia menarik arus listrik secara mendadak dan terputus-putus (seperti denyut nadi yang sangat cepat). Karena kabel dari sumber listrik (baterai) memiliki hambatan, tarikan arus mendadak ini menyebabkan tegangan di kaki chip sempat turun/drop sesaat (misal dari 3.3V turun jadi 3.0V lalu naik lagi). Jika tegangan turun terlalu jauh, chip akan mati atau restart sendiri.
        * Cara kerja:
            * Kapasitor dipasang paralel (antara Positif dan Negatif) sedekat mungkin dengan chip.
            * Kapasitor ini menyimpan sedikit muatan listrik lokal.
            * Saat chip menarik arus besar secara mendadak, chip mengambil kekurangan arus dari Kapasitor tersebut, bukan menunggu dari baterai yang jauh.
            * Hasilnya, tegangan di kaki chip tetap rata dan stabil (tidak anjlok).
        * Tujuan: Mencegah tegangan drop saat kerja berat.

    * Power On Reset (POR)
        * Fungsi: Menunda chip bekerja sampai tegangan stabil.
        * Lokasi Pasang: Di kaki RESET chip.
        * Rangkaian umum -> Input masuk ke Resistor, lalu kaki Kapasitor disambung ke Ground. Output diambil di antara R dan C.
        * Kapan Berfungsi: Hanya satu kali, yaitu saat alat baru dinyalakan.
        * Masalah: Saat Anda menyalakan alat, tegangan listrik dari baterai atau adaptor tidak langsung stabil (misal langsung 5 Volt). Tegangan itu naik secara bertahap (0V -> 2V -> 4V -> 5V). Jika chip (otak) dipaksa bekerja saat tegangan masih rendah (misal di 2V), chip bisa error atau macet.
        * Cara kerja:
            * Rangkaian POR (Resistor + Kapasitor) dipasang di kaki RESET chip.
            * Saat listrik baru masuk, Kapasitor butuh waktu untuk terisi tegangan.
            * Selama Kapasitor belum penuh, ia akan mengirim sinyal 0 (LOW) ke kaki Reset. Ini memaksa chip untuk "diam" dulu.
            * Setelah beberapa milidetik, Kapasitor penuh. Sinyal berubah menjadi 1 (HIGH).
            * Chip berhenti di-Reset dan mulai bekerja. Saat ini, tegangan sumber listrik dipastikan sudah stabil di 5V.
        * Tujuan: Memberi jeda waktu start-up.

    * Switch Debouncing (Peredam Tombol)
        * Fungsi: Membersihkan sinyal "kotor" dari tombol/switch agar terbaca sebagai satu kali tekanan yang bersih (menghilangkan noise).
        * Lokasi Pasang: Di antara Tombol Fisik dan Pin Input (GPIO) mikrokontroler.
        * Kapan Berfungsi: Setiap kali tombol ditekan atau dilepas.
        * Masalah: Tombol fisik terbuat dari pelat logam. Saat ditekan, logam tersebut tidak langsung menempel sempurna, melainkan "membal" (bouncing) atau bergetar selama beberapa milidetik (seperti bola pingpong yang dijatuhkan). Chip yang kerjanya super cepat (MHz) akan membaca getaran ini sebagai sinyal: Nyambung-Putus-Nyambung-Putus berulang kali dalam waktu singkat. Akibatnya, satu kali tekan tombol bisa terbaca sebagai 10 kali klik oleh program.
        * Cara kerja:
            * Rangkaian RC (Resistor + Kapasitor) dipasang di jalur input tombol.
            * Saat tombol ditekan dan kontak logam bergetar (membuat sinyal naik-turun cepat/High Frequency), Kapasitor bertindak sebagai "Shock Breaker" atau peredam kejut.
            * Kapasitor akan menyerap lonjakan-lonjakan tegangan cepat tersebut (membuangnya ke Ground).
            * Kapasitor memaksa tegangan input berubah secara halus/melengkung, bukan patah-patah tajam mengikuti getaran tombol.
            * Chip mikrokontroler akhirnya hanya melihat satu perubahan logika yang mulus (misal dari HIGH ke LOW) tanpa gangguan getaran.
        * Tujuan: Mencegah double-click hantu atau pembacaan input yang error.

**intinya kalau series dan parallel itu disederhanakan dulu**

**implementasi utama capacitor yaitu Bypass, POR, Debouncing**

**dalam rangkaian RC bisa lebih dari 1 resistor dan lebih dari 1 capacitor**

**ukuran resistor dan capacitor mempengaruhi waktu tunda timer**
