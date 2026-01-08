# Introduction

### Rangkaian
- PLN (220V AC) -> Adapter -> 9V/12V DC (Masih agak "kasar") -> Regulator (LDO/Buck) -> 3.3V Presisi (Untuk ESP32).

### Tegangan Liar vs. Kebutuhan Presisi
- Tegangan dari sumber listrik PLN itu merupakan tegangan liar 
- Dalam pengembangan kita butuh yang presisi
- e.g esp32 butuh 3.3V tapi dari PLN adanya 220VAC 
- maka butuh adapter lalu perantara

### Adapter
- Input PLN 220VAC
- dengan trafo diturunkan VACnya 
- lalu dengan bridge rectifier dibuat menjadi DC (tapi masih sinusoidal bisa balik ke 0V)
- ditambah capacitor ripple sehingga sinyal DC menjadi lebih datar tidak balik ke 0V (walaupun terkadang masih bergerigi ada sisaan AC makanya perlu perantara) 
- Output 9V

### Perantara 
- Linear Regulator
    - Contoh: LM7805 (Standard Regulator)
    - Input 9V 
    - Output 5V
    - Maka selisih 4V akan dibuang menjadi panas
    - Tidak Efisien
    - Intinya linear regulator itu menahan aliran (seperti kran yang ditutup separuh makanya bisa panas)
- LDO (Low Dropout Regulator)
    - Contoh: AMS1117, LD29150
    - Merupakan Linear Regulator yang butuh selisih tegangan (dropout) sangat kecil.
    - Input 5.4V (Bisa sangat dekat dengan output)
    - Dropout 0.4V (Contoh)
    - Output 5V
    - Lebih efisien karena bisa diberi input yang lebih rendah (misal 5.4V) dibandingkan regulator biasa.
- Switching Regulator
    - Contoh: Buck Converter, Boost Converter
    - Input 9V
    - Output 5V
    - minim ada panas
    - Intinya switching regulator itu memotong-motong aliran (krannya dibuka FULL lalu menutupnya FULL ribuan kali per detik jadi tidak membuang kelebihan dan menjadi panas tapi mengonversi daya)

### Implementasi Perantara
- untuk perantara pakai 2 stage:
    - stage 1 
        - menggunakan switching regulator (menurunkan e.g 9V ke 5V)
        - hasil: minim panas
    - stage 2 
        - menggunakan LDO (menurunkan e.g 5V ke 3.3V)
        - hasil: tegangan menjadi sangat halus

### Power Supply Design
- Stage 1 - Rectification dan Filtering
    - Bridge Rectifier
    - Capacitor Ripple
- Stage 2 - Regulation
    - Switching Regulator
    - LDO

### Perbedaan
- Perbedaan mendasar switching regulator dan Linear regulator yaitu 
    - Switching hasilnya masih bergerigi 
    - Linear hasilnya lurus mulus