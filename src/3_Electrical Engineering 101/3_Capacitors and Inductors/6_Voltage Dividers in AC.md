# Voltage Dividers in AC
- Filtering berdasarkan frekuensi

### contoh
- f = 100 Hz
- R = 200 ohm -> ZR = 200∠0° Ω
- L = 2.2 mH, maka 
  - XL = 2πfL = 2π(100)(2.2×10^-3) = 1.38 Ω
  - ZL = XL∠90° = 1.38∠90° Ω

### Skenario RL dan LR
- Skenario 1:
  - R dulu baru L (output diambil di Induktor)
  - Vout = Vin * (ZL / (ZL + ZR))
  - Saat frekuensi rendah (Hz):
    - ZL sangat kecil, sehingga Vout mendekati 0
    - Efek: Sinyal diblokir
  - Saat frekuensi tinggi (Hz):
    - ZL sangat besar, sehingga Vout mendekati Vin
    - Efek: Sinyal diloloskan
  - Skenario 1 ini disebut High Pass Filter (HPF) -> frekuensi tinggi maka ZL tinggi maka tegangan diloloskan
- Skenario 2:
  - L dulu baru R (output diambil di Resistor)
  - Vout = Vin * (ZR / (ZR + ZL))
  - Saat frekuensi rendah (Hz):
    - ZL sangat kecil, sehingga Vout mendekati Vin
    - Efek: Sinyal diloloskan
  - Saat frekuensi tinggi (Hz):
    - ZL sangat besar, sehingga Vout mendekati 0
    - Efek: Sinyal diblokir
  - Skenario 2 ini disebut Low Pass Filter (LPF) -> frekuensi rendah maka ZL rendah maka tegangan diloloskan

### Trivia
- Vout ini diambil di antara R dan L atau di antara L dan R
- Sinyal yang diloloskan ini yaitu tegangan AC
- Voltage Dividers di AC bisa juga menggunakan Capacitor dan konsepnya sama dengan Inductor.

### Contoh lain
- R = 100 ohm -> ZR = 100∠0° Ω
- C = 100 nF, maka 
  - XC = 1/(2πfC) = 1/(2π(100)(100×10^-9)) = 1591.5 Ω
  - ZC = XC∠-90° = 1591.5∠-90° Ω

### Skenario RC dan CR
- Skenario 1:
  - R dulu baru C (output diambil di Capacitor)
  - Vout = Vin * (ZC / (ZC + ZR)) -> tegangan yang diloloskan
  - Saat frekuensi rendah (Hz):
    - ZC sangat besar, sehingga Vout mendekati Vin
    - Efek: Sinyal diloloskan
  - Saat frekuensi tinggi (Hz):
    - ZC sangat kecil, sehingga Vout mendekati 0
    - Efek: Sinyal diblokir
  - Skenario 1 ini disebut Low Pass Filter (LPF) -> frekuensi rendah maka ZC besar maka tegangan diloloskan
- Skenario 2:
  - C dulu baru R (output diambil di Resistor)
  - Vout = Vin * (ZR / (ZR + ZC)) -> tegangan yang diloloskan
  - Saat frekuensi rendah (Hz):
    - ZC sangat besar, sehingga Vout mendekati 0
    - Efek: Sinyal diblokir
  - Saat frekuensi tinggi (Hz):
    - ZC sangat kecil, sehingga Vout mendekati Vin
    - Efek: Sinyal diloloskan
  - Skenario 2 ini disebut High Pass Filter (HPF) -> frekuensi tinggi maka ZC kecil maka tegangan diloloskan


- **ZL dan XL berbanding lurus dengan frekuensi**
- **ZC dan XC berbanding terbalik dengan frekuensi**
