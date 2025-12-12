# Capacitors and AC Coupling

* capacitor
    * menstabilkan tegangan, menghilangkan noise
    * satuannya yaitu Farad (F)

### Fungsi Capacitor
    * Low Pass Filter: Meloloskan sinyal pelan (Bass), membuang sinyal cepat (Treble/Noise). Dipakai untuk membersihkan sinyal sensor yang jittery (gemetar). rangkaiannya resistor dulu baru capacitor.
    * High Pass Filter: Meloloskan sinyal cepat, memblokir sinyal diam (DC). Dipakai di audio amplifier agar tegangan baterai tidak masuk ke speaker. rangkaiannya capacitor dulu baru resistor.

### Series and Parallel Capacitor
* Parallel Capacitor
    * Ct = C1 + C2 + C3 + ...
* Series Capacitor 
    * Ct = C1 * C2 / (C1 + C2)
    * Capacitor disusun series sangat jarang sekali digunakan, mending langsung pasang capacitor yang besar   

### Konsep RC Circuit
    * Konsep Rangkaian RC (Resistor + Capacitor) = TIMER
    * Ini adalah konsep paling vital untuk logika digital dan mikrokontroler.
    * Jika Anda menghubungkan Resistor dan Kapasitor secara seri (berurutan), listrik tidak akan langsung "penuh" tapi berangsung akan penuh.
    * Kapasitor akan terisi secara perlahan mengikuti kurva melengkung.
    * Rumus Waktu (T) -> Waktu (detik) = R (Ohm) * C (Farad)
    * Kapasitor dianggap penuh (100%) setelah 5 * R * C. 
    * Contoh:Anda menekan saklar. Lampu tidak langsung nyala terang, tapi meredup dulu baru terang perlahan. Itu efek rangkaian RC. 
    

### Implementasi dari Low Pass Filter
    * Power On Reset (POR)
        * Fungsi: Menunda chip bekerja sampai listrik stabil.
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

### Coloumb
* Q = C * V
* C -> Kapasitor -> Farad (F)
* V -> Voltase -> Volt (V)
* Q -> Muatan -> Coloumb (C)

__intinya kalau series dan parallel itu disederhanakan dulu__

