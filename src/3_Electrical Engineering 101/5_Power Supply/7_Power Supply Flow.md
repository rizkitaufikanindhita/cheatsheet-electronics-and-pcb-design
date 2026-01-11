# Alur Power Supply

### ZONA 1: Konversi Kasar (AC ke DC Mentah)
__Ini biasanya ada di dalam kotak adaptor/wall wart atau bagian power supply utama.__

1. PLN (220V AC)
2. Trafo (Turun ke 12V AC)
3. Bridge Rectifier (Ubah ke DC gelombang)
4. Capacitor Ripple (Elco Besar) (Ratakan jadi DC 12V - tapi masih ada ripple)


### ZONA 2: Proteksi & Pra-Regulasi
1. PTC Fuse
    - Posisi: Tepat setelah colokan DC Jack.
    - Fungsi: Kalau ada korsleting di PCB kamu, dia putus duluan sebelum adaptor atau trafo kamu terbakar.

2. TVS Diode
    - Posisi: Setelah Fuse.
    - Fungsi: Kalau tiba-tiba ada petir atau lonjakan listrik dari adaptor, dia "makan" lonjakannya biar gak ngerusak regulator.

3. Switching Regulator (Opsional tapi bagus)
    - Fungsi: Turunkan 12V ke 7V dengan efisien (tidak panas).

4. Ferrite Bead (L)
    - Posisi: Setelah Regulator.Di jalur positif sebelum masuk LDO.
    - Fungsi: Memblokir noise frekuensi tinggi dari Switching Regulator (karena switching itu berisik) atau dari kabel panjang, supaya tidak masuk ke LDO.

### ZONA 3: Regulasi Halus (Final Stage)
__Ini zona suci untuk MCU__

1. Kapasitor Input LDO (Besar + Kecil/Bypass) 
    - Posisi: Tepat di kaki input LDO.
    - Fungsi: Decoupling & Bypass noise sisa-sisa.

2. LDO (Linear Regulator) 
    - Fungsi: Menurunkan 7V ke 3.3V (atau 5V) dengan sangat halus/stabil. LDO membuang sisa noise (Ripple Rejection).

3. Kapasitor Output LDO
    - Fungsi: Menjaga kestabilan output LDO.

4. MCU (ESP32) 
    - Hasil: Mendapat suplai 3.3V yang super bersih dan stabil.