# Power Supply Primer

- Listrik PLN (AC 220V)
- Trafo -> menurunkan VAC PLN (AC 12V)
- Bridge Rectifier -> membuat menjadi VDC tapi masih kembali ke 0V (DC 12V)
- Capacitor Ripple -> membuat VDC tidak kembali ke 0V (DC 12V)
- Switching Regulator -> menurunkan VDC (Tapi masih agak bergerigi) (DC 7V)
- LDO -> menurunkan VDC dan membuat V lurus sempurna (DC 5V)
- VIN MCU (DC 3.3V)

### Deep Dives bagian LDO 
- dibagian LDO ini ouputnya yang masuk ke pin VIN MCU
- Alur
    - Input dari Switching Regulator (e.g 7V)
    - Lalu pasang kapasitor ganda di input (sebelum masuk LDO(IC)) (bypass)
        - kapasitor keramik (0.1uF/100nF) -> untuk frekuensi tinggi
        - kapasitor elco (10uF/47uF) -> untuk frekuensi rendah
    - Pasang LDO/IC dengan heatsink
        - Kaki 1 (kiri) -> input
        - Kaki 2 (tengah) -> ground
        - Kaki 3 (kanan) -> output
    - Pasang Diode 
        - Katoda disambung ke jalur input (kaki 1) LDO
        - Anoda disambung ke jalur output (kaki 3) LDO
    - Lalu pasang kapasitor ganda di output (sebelum keluar LDO(IC)) (bypass) (.e.g output LDO 5V masuk ke pin VIN (bukan VCC) MCU, lalu AMS onboard mengubahnya menjadi 3.3V untuk otak chip MCU)
        - kapasitor keramik (0.1uF/100nF) -> untuk frekuensi tinggi
        - kapasitor elco (10uF/47uF) -> untuk frekuensi rendah
