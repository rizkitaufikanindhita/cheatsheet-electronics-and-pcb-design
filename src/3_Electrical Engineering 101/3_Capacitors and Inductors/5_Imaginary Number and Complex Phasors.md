# Imaginary Number and Complex Phasors

- Aturan Operasi Bilangan Kompleks
  - Penjumlahan
    - Jumlahkan komponen yang sejenis. Real dengan Real, Imajiner dengan Imajiner.
    - (a+jb) + (c+jd) = (a+c) + j(b+d)
  - Perkalian
    - Amplitude -> dikalikan
    - Sudut -> ditambahkan
  - Pembagian
    - Amplitude -> dibagi
    - Sudut -> dikurangkan

- e.g ada rangkaian RL
  - Sumber v(t) = 20sin(1000t)
  - Amplitudo (Vmax) = 20V
  - Kecepatan Sudut (ω) = 1000 rad/s
  - Fase (φ) = 0 derajat
  - komponen:
    - Resistor (R) = 3 Ω
    - Induktor (L) = 4 mH = 0.004 H
  - Langkah-langkah:
    - Ubah tegangan ke Phasor -> V = 20∠0° Volt
    - Ubah komponen ke Impedansi 
      - Resistor -> R = 3 Ω
      - Induktor -> XL = ωL = 1000 x 0.004 = 4 Ω
      - Impedansi -> Z = R + jXL = 3 + j4 Ω
    - Hitung Amplitude -> |Z| = sqrt(R^2 + XL^2) = sqrt(3^2 + 4^2) = 5 Ω
    - Hitung Sudut -> φ = tan^-1 x (XL/R) = 53.1°
    - Gabung dalam format Phasor -> Z = A∠φ -> Z = 5∠53.1° Ω 
    - Hitung Arus
      - I = V / Z = 20∠0° Volt / 5∠53.1° Ω = 4∠-53.1° Ampere
      - i(t) = 4sin(1000t-53.1°) Ampere
      - maka ELI -> tegangan lebih dulu daripada arus, dimana arus dibelakang tegangan sebesar 53.1 derajat.
    - Hitung Tegangan masing masing komponen
      - VR = I * R = 4∠-53.1° Ampere x 3∠0° Ohm = 12∠-53.1° Volt
      - VL = I * XL = 4∠-53.1° Ampere x 4∠90° Ohm = 16∠36.9° Volt
      - Vt = sqrt(VR^2 + VL^2) = sqrt(12^2 + 16^2) = 20 Volt
    - Result Summary
      - I = 4∠-53.1° Ampere (Peak)
      - I = 4 x 0.707 = 2.828 Ampere (RMS)
      - VR = 12∠-53.1° Volt
      - Sudut I dan VR pada derajat yang sama 
      - VL = 16∠36.9° Volt (Peak)
      - VL = 16 x 0.707 = 11.314 Volt (RMS)
    - **Ingat I , VR dan VL menggunakan peak bukan RMS** 

### Summary
- intinya dalam analisis rangkaian AC
  - Hitung I dengan V dan Z (karena pada sinyal AC) serta sudutnya
  - Hitung Z dan Sudut -> dari resistor dan reactance (induktor dan atau kapasitor)

**Amplitude == Magnitude**
