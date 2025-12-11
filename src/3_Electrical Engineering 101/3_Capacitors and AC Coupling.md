# Capacitors and AC Coupling

* capacitor
    * menstabilkan tegangan, menghilangkan noise
    * satuannya yaitu Farad (F)

* konsep rangkaian RC (Resistor dan Capacitor)
    * Resistor dan Capacitor dihubungkan secara series 
    * Rangkaian umum -> Input masuk ke Resistor, lalu kaki Kapasitor disambung ke Ground. Output diambil di antara R dan C.
    * Tujuan -> menghilangkan noise dan Power On Reset (POR)

* Fungsi Capacitor
    * Low Pass Filter: Meloloskan sinyal pelan (Bass), membuang sinyal cepat (Treble/Noise). Dipakai untuk membersihkan sinyal sensor yang jittery (gemetar). rangkaiannya resistor dulu baru capacitor.
    * High Pass Filter: Meloloskan sinyal cepat, memblokir sinyal diam (DC). Dipakai di audio amplifier agar tegangan baterai tidak masuk ke speaker. rangkaiannya capacitor dulu baru resistor.

* Implementasi dari Low Pass Filter
    * Power On Reset (POR)
        * Fungsi: Menunda chip bekerja sampai listrik stabil.
        * Lokasi Pasang: Di kaki RESET chip.
        * Kapan Berfungsi: Hanya satu kali, yaitu saat alat baru dinyalakan.
        * Masalah: Saat Anda menyalakan alat, tegangan listrik dari baterai atau adaptor tidak langsung stabil (misal langsung 5 Volt). Tegangan itu naik secara bertahap (0V $\rightarrow$ 2V $\rightarrow$ 4V $\rightarrow$ 5V). Jika chip (otak) dipaksa bekerja saat tegangan masih rendah (misal di 2V), chip bisa error atau macet.
        * Cara kerja: 
            * Rangkaian POR (Resistor + Kapasitor) dipasang di kaki RESET chip.
            * Saat listrik baru masuk, Kapasitor butuh waktu untuk terisi tegangan.
            * Selama Kapasitor belum penuh, ia akan mengirim sinyal 0 (LOW) ke kaki Reset. Ini memaksa chip untuk "diam" dulu.
            * Setelah beberapa milidetik, Kapasitor penuh. Sinyal berubah menjadi 1 (HIGH).
            * Chip berhenti di-Reset dan mulai bekerja. Saat ini, tegangan sumber listrik dipastikan sudah stabil di 5V.
        * Tujuan: Memberi jeda waktu start-up.
    
    * Bypass / Decoupling Capacitor
        * Fungsi: Menstabilkan tegangan suplai tepat di kaki chip.
        * Lokasi Pasang: Di kaki VCC.
        * Kapan Berfungsi: Terus-menerus selama alat menyala.
        * Masalah: Chip digital (seperti ESP32) bekerja dengan kecepatan sangat tinggi. Ia menarik arus listrik secara mendadak dan terputus-putus (seperti denyut nadi yang sangat cepat). Karena kabel dari sumber listrik (baterai) memiliki hambatan, tarikan arus mendadak ini menyebabkan tegangan di kaki chip sempat turun/drop sesaat (misal dari 3.3V turun jadi 3.0V lalu naik lagi). Jika tegangan turun terlalu jauh, chip akan mati atau restart sendiri.
        * Cara kerja: 
            * Kapasitor dipasang paralel (antara Positif dan Negatif) sedekat mungkin dengan chip.
            * Kapasitor ini menyimpan sedikit muatan listrik lokal.
            * Saat chip menarik arus besar secara mendadak, chip mengambil kekurangan arus dari Kapasitor tersebut, bukan menunggu dari baterai yang jauh.
            * Hasilnya, tegangan di kaki chip tetap rata dan stabil (tidak anjlok).
        * Tujuan: Mencegah tegangan drop saat kerja berat.

