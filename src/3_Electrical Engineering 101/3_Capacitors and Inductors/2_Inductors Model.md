# Inductors Model

- Konsep
  - Simpan energi pada medan magnet
  - Tujuan : **menstabilkan arus**
  - Satuannya yaitu Henry (H)
  - Symbol : L 
  - t = 5 x (L/R) yaitu untuk menghitung waktu delay sampai induktor penuh dan arus menjadi stabil.
  - Komponen ini bereaksi terhadap Perubahan Arus.
  - Rumus 
    - Rumus Energizing dan De-Energizing
      - Energizing
        - I(t) = I(0) * (1 - e^(-t/(L/R)))
        - Arus naik dari 0 Ampere menuju arus maksimal
      - De-Energizing
        - I(t) = I(0) * e^(-t/(L/R))
        - Arus turun dari I(0) perlahan menuju 0 Ampere.
    - Rumus jumlah tegangan listrik yang mengalir menembus (secara efektif) induktor. 
      - V = L * dI/dt
      - Besar Tegangan (V) tergantung pada seberapa cepat Arus berubah (dI/dt)
      - Kasus 1: Arus Tiba-tiba DROP (Turun/Putus) Terjadi perubahan arus negatif (nilai dI/dt negatif). Berdasarkan rumus, Induktor menghasilkan Tegangan "dorong" ke depan. Efek: Arus tidak bisa berhenti seketika, tapi akan "bablas" atau terus mengalir sebentar meskipun sumber sudah mati. (Analogi: Truk yang sedang ngebut tiba-tiba direm mendadak (Arus Drop). Karena truknya sangat berat, ia tidak bisa langsung berhenti di tempat, tapi akan terseret/meluncur jauh ke depan sebelum benar-benar berhenti.)
      - Kasus 2: Arus Tiba-tiba SPIKE (Naik/Nyala) Terjadi perubahan arus positif (nilai dI/dt positif). Berdasarkan rumus, Induktor menghasilkan Tegangan "lawan" ke belakang. Efek: Arus tertahan, sehingga tidak bisa langsung ngebut, melainkan naik perlahan-lahan. (Analogi: Truk yang sedang diam tiba-tiba di-gas pol (Arus Spike). Karena muatannya sangat berat, truk itu terasa berat sekali untuk mulai bergerak, kecepatannya naik pelan-pelan, tidak bisa langsung melesat seperti mobil balap.)

- Series dan Parallel Inductor
  - sama seperti resistor
  - Series Inductor
    - Lt = L1 + L2 + L3 + ...
  - Parallel Inductor
    - Lt = L1 x L2 / (L1 + L2)

- Di Embedded System: Anda jarang memasang induktor fisik (kecuali untuk filter power supply). Namun, Anda harus waspada terhadap Induktansi Parasitik (induktansi tak sengaja pada kabel panjang). Hal ini menyebabkan sinyal digital menjadi "kotor" atau bergelombang (ringing), yang bisa merusak data komunikasi antar chip. solusi pada PCB yang bisa dilakukan perpendek jalur, pelebar jalur, meminimalkan vias, Differential Pairs dan Solid Ground Plane (Lapisan Ground Utuh).

**Inductor bekerja ketika arus berubah**
