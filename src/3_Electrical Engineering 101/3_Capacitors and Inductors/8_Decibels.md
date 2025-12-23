# Decibels

### Konsep Decibels
- Di electro akan banyak 0 -> disederhanakan dengan decibels
- dB ini menggantikan H(f) agar lebih simple terkait 0 nya
- 100 -> 2 bel -> 20 dB
- 1000 -> 3 bel -> 30 dB
- 0.01 -> -2 bel -> -20 dB
- hukum dasar dB itu untuk **DAYA** (Watt) -> rumusnya 10 log
- tapi kalau dipakai di **TEGANGAN** (Volt) -> P = V^2/R -> maka kalau tegangan rumusnya 20 log
- e.g
    - Daya
        - 100 Watt -> 2 bel x 10 -> 20 dB
        - 1000 Watt -> 3 bel x 10 -> 30 dB
    - Tegangan
        - 100 Volt -> 2 bel x 20 -> 40 dB
        - 1000 Volt -> 3 bel x 20 -> 60 dB

### Cutoff Frequency
- batas dB -> -3 dB -> dikali 0.707 -> Vout = Vin x 0.707, dibawah nilai Vout ini chip ada kemungkinan akan menilai 0 (false)

### dB Absolut 
- Patokan (Referensi)
    - Power
        - dBm -> milliwatt
        - pengalinya 10
        - jangkar/patokannya -> 0 dBm == 1 milliwatt
        - e.g
            - +10 dBm -> 10 x 1 mW = 10 mW  
            - +20 dBm -> 100 x 1 mW = 100 mW
            - -30 dBm -> 0.001 x 1 mW = 0.001 mW
    - Voltage
        - dBV -> Volt
        - pengalinya 20
        - jangkar/patokannya -> 0 dBV == 1 Volt
        - e.g
            - +20 dBV -> 10 x 1 Volt = 10 Volt
            - +40 dBV -> 100 x 1 Volt = 100 Volt
            - -20 dBV -> 0.1 x 1 Volt = 0.1 Volt
