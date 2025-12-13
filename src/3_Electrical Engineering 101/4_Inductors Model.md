# Inductors Model

- Konsep
  - Simpan energi pada medan magnet
  - Tujuan : menstabilkan arus
  - Satuannya yaitu Henry (H)
  - Symbol : L 
  - 5 x (L/R) yaitu untuk menghitung waktu delay sampai induktor penuh dan arus menjadi stabil

- Series dan Parallel Inductor
  - sama seperti resistor
  - Series Inductor
    - Lt = L1 + L2 + L3 + ...
  - Parallel Inductor
    - Lt = L1 x L2 / (L1 + L2)

- Di Embedded System: Anda jarang memasang induktor fisik (kecuali untuk filter power supply). Namun, Anda harus waspada terhadap Induktansi Parasitik (induktansi tak sengaja pada kabel panjang). Hal ini menyebabkan sinyal digital menjadi "kotor" atau bergelombang (ringing), yang bisa merusak data komunikasi antar chip. solusi pada PCB yang bisa dilakukan perpendek jalur, pelebar jalur, meminimalkan vias, Differential Pairs dan Solid Ground Plane (Lapisan Ground Utuh).
