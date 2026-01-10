# Frequency Domain Analysis

- sebelumnya hitung I dan V pada rangkaian RL atau RC yang dialiri sinyal AC hanya pada **frekuensi tertentu** (**snapshot**). e.g hanya pada 100Hz
- sekarang hitung I dan V pada rangkaian RL atau RC yang dialiri sinyal AC pada berbagai frekuensi (terus menerus) (frequency domain analysis). e.g dari 1Hz - 200Hz

### Implementasi 
- Case Rangkaian RC
    - Masalah : 
        - Anda memutar potensiometer ke posisi tengah. Tangan Anda diam, tapi angka di Serial Monitor tidak stabil. 
        - Harapan: 2048 (stabil). 
        - Kenyataan: 2048, 2055, 2042, 2060... (lompat-lompat/jitter).
        - Rangkaiannya RC
    - Analisis : 
        - Gerakan Tangan Anda: Lambat. (Frekuensi Rendah / < 5 Hz). -> Wajib Lolos.
        - Jitter (Noise): Cepat/Getar. (Frekuensi Tinggi / > 50 Hz). -> Wajib Diblokir.
        - Artinya tujuan kita agar potentiometer ini hanya membaca dari gerakan tangan kita saja (yang lambat Hz nya).
    - Solusi :
        - Karena pengen frekuensi rendah yang lewat bukan yang tinggi maka pakai **Low Pass Filter**.
        - Tentukan Cutoff -> 15 Hz, diatas itu akan diblokir
    - Implementasi :
        - Resistor -> 1 kΩ
        - Capacitor -> 10 µF (kapasitor ditentukan dulu baru resistor karena resistor banyak jenisnya)
        - Vinnya dari potentiomter -> 3.3V
        - Voutnya esp32
    - Rumus Cutoff Frekuensi untuk diloloskan:
        - fc = 1/2πRC
        - fc = 1/6.28 x 1000 x 0.00001
        - fc = 15.9 Hz 
    - Summary :
        - frekuensi 15.9 Hz ada ambang batas sinyal akan diloloskan karena frekuensinya rendah. 
        - Gerakan tangan (1 Hz) jauh di bawah batas -> Lolos.
        - Noise listrik (50 Hz) jauh di atas batas -> Diblokir.
    - Hitung tegangan yang lolos (H(f)) -> transfer function
        - f = 1 Hz -> pakai tangan
        - H(f) = 1/sqrt(1+(2πfRC)^2)
        - H(f) = 0.99 -> 99 % tegangan lolos
        - Vout = Vin x H(f) 
        - Vout = 3.3 x 0.99 -> 3.29 V yang lolos
        
        - f = 15.9 Hz -> batas
        - H(f) = 1/sqrt(1+(2πfRC)^2)
        - H(f) = 0.707 -> 70.7 % tegangan lolos        
        - Vout = 3.3 x 0.707 -> 2.33 V yang lolos
        - 0.707 sama dengan -3db (ambang batas sebelum berangsur-angsur diblokir)

        - f = 50 Hz -> noise listrik
        - H(f) = 1/sqrt(1+(2πfRC)^2)
        - H(f) = 0.30 -> 30 % tegangan lolos

        - semaking tinggi frekuensi semakin rendah tegangan yang lolos karena diblokir
    
- Kalau Rangkaian RL, 
    - rumus
        - cutoff frekuensi -> fc = R/2πL
        - presentase yang lolos 
            - Low Pass Filter -> H(f) = 1/sqrt(1+(f/fc)^2), dimana fc -> cutoff frequency, f -> frequency input
            - High Pass Filter -> H(f) = 1/sqrt(1+(fc/f)^2), dimana fc -> cutoff frequency, f -> frequency input

### Implementasi lain rangkaian RC ataupun C
- Bypass / Decoupling Capacitor (tidak perlu pakai resistor)
- Power On Reset (POR)
- Switch Debouncing

### trivia 
-**kalau Voutnya terlalu kecil maka akan dibaca 0 oleh microcontroller**

### trivia 
-**Solusi Engineering:**
-**Jika Anda butuh Cutoff tinggi (15.9 kHz), JANGAN mengecilkan Resistor sampai ekstrem (<300 Ohm).Tapi Kecilkan Kapasitornya.**
-**Cara Salah: R = 100 Ohm, C = 0.1 μF, fc = 15.9 kHz (Tapi arus kegedean, alat jebol/drop).**
-**Cara Benar: R = 1000 Ohm, C = 0.01 μF, fc = 15.9 kHz (Arus aman, sinyal bersih).**
-**Safety Rule: Jangan gunakan nilai Resistor terlalu kecil (misal < 300 Ohm) sebagai filter input, karena akan membebani sensor atau sumber sinyal Anda. Lebih baik mainkan nilai Kapasitornya.**

### trivia 
-**Membuat filter lebih tajam (Noise hilang lebih cepat).**
-**2 atau lebih Rangkaian Filter dipasang seri.**
-**Htotal(f) = H1(f) x H2(f)**
-**agar berhasil bisa pakai Op-Amp (Operational Amplifier) komponen diantara filter**
-**atau pakai Impedance Scaling, Filter 1: R = 100 Ohm, L = 10 mH lalu Filter 2: R = 1.000 kOhm, L = 100 mH.**