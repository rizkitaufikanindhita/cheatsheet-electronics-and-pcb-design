# AC
- Inti materi menghitung I dan V pada rangkaian seri pada sinyal AC

### Sinyal AC
- rumus untuk mendeskripsikan perilaku AC yang berubah-ubah.
- V(t) = A * sin(ωt + φ)
- A = V * 1.414
- cara baca:
  - "Sinyal ini tingginya segini (A), getarnya secepat ini (ω), dan posisinya sekarang ada di sudut sekian (φ)."

### PHASOR (Phase Vector)
- menghilangkan sin(ωt) dan hanya ambil A dan φ karena nilai sin(ωt) sama terus.
- sehingga e.g V(t) = A * sin(ωt + φ) dapat ditulis sebagai V = A∠φ (A pada sudut φ derajat), bisa untuk arus dengan I = B∠φ(B pada sudut φ derajat), A dan B adalah amplitudo dari sinyal AC.

![phasor](../img/Phasor.png)
- R, L, C saat dialiri AC
  - pada rangkaian AC, resistor kan I dan V pada satu phase maka bisa pakai ohm's law, namun pada induktor dan kapasitor yang I dan Vnya tidak satu phase tetap masih bisa pakai ohm's law tapi lebih tepatnya dengan memperhatikan reactance (X) dan impedance (Z).
  - pada induktor dan kapasitor kan dirangkaian tidak ada resistor maka dalam menentukan arus menggunakan reactance.
  
### Perbedaan 
- Resistor (R): Menghambat arus dengan cara "gesekan" elektron, yang sifatnya tetap/konstan tidak peduli seberapa cepat frekuensi arusnya.
- Reaktansi (X): Menghambat arus akibat reaksi penyimpanan energi (medan listrik atau magnet), dan nilainya berubah-ubah tergantung frekuensi sinyal AC. 
**frekuensi itu Hz -> seberapa sering sinyal berubah dalam satu detik**

### Reactance (X)
- adalah hambatan yang muncul bukan karena gesekan elektron (seperti pada Resistor), melainkan karena reaksi komponen terhadap perubahan arus atau tegangan.
- Capacitor:
  - rumus konversi capacitor ke reactance (X)
  - Xc = 1 / (ωC)
  - mekanisme:
    - Frekuensi Rendah: Tegangan berubah lambat. Kapasitor punya banyak waktu hingga penuh. Saat penuh, arus berhenti mengalir (terblokir). Hambatan (Xc) besar.
    - Frekuensi Tinggi: Tegangan bolak-balik sangat cepat. Kapasitor belum sempat penuh, arah arus sudah berbalik lagi. Karena tidak pernah penuh, arus terus mengalir leluasa bolak-balik. Hambatan (Xc) menjadi kecil.
  - f tinggi, Xc kecil
  - f turun, Xc besar
- Inductor:
  - rumus konversi inductor ke reactance (X)
  - XL = ωL
  - mekanisme:
    - Frekuensi Rendah: Arus berubah pelan-pelan. Tegangan lawan yang dihasilkan kecil. Hambatan (XL) kecil.
    - Frekuensi Tinggi: Arus berubah sangat cepat. Induktor merespons dengan menciptakan tegangan lawan yang sangat besar untuk melawan perubahan itu. Akibatnya, arus sulit lewat. Hambatan (XL) menjadi besar.
  - f tinggi, XL besar
  - f turun, XL kecil

### Peta Phasor
- Sumbu Datar (X): Adalah jalan untuk Resistor (R). Arahnya ke kanan.
- Sumbu Tegak (Y): Adalah jalan untuk Reaktansi (X).
  - Induktor (XL): Jalan ke Utara (Atas/Positif).
  - Kapasitor (XC): Jalan ke Selatan (Bawah/Negatif).

### Impedansi (Z)
- Impedansi adalah total penghambat arus antara Resistor (nyata) dan Reaktansi (imajiner). 
- rumus 
  - Z = R + jX
  - R = Jumlah Hambatan nyata (jumlah resistor)
  - X = Jumlah Hambatan imajiner (jumlah inductor dan kapasitor)
- rumus 
  - Z = sqrt(R^2 + X^2)
  - untuk menghitung Impedansi hasilnya ohm 
  - yang akan digunakan untuk ohm's law
  - Jika ada Kapasitor (XC) dan Induktor (XL) sekaligus dalam satu rangkaian seri, mereka akan saling bertarung (saling mengurangi).
  
### Summary
- Dalam rangkain AC untuk menghitung arus, kita menggunakan Impedansi (Z) yang merupakan total penghambat arus antara Resistor (nyata) dan Reaktansi (imajiner). 
- Urutannya:
  - Ubah kapasitor dan atau induktor menjadi reactance (X)
  - Hitung Impedansi (Z)
  - Hitung arus (I) dengan Ohm's Law
  - Hitung tegangan (V) masing-masing komponen baik pada resistor, inductor, dan atau kapasitor (V = I * Z). Biasanya jika dijumlahkan akan berbeda dengan Vs (Tegangan Sumber) karena karena perlu menggunakan pythagoras untuk menghitung tegangan total. Vt = sqrt(Vr^2 + Vi^2)
  - Jika ada V dari Induktor (XL) dan Kapasitor (XC) sekaligus dalam satu rangkaian seri, mereka akan saling bertarung (saling mengurangi). Vt = sqrt(Vr^2 + (Vl - Vc)^2)
  - Hitung sudut fase (φ), e.g Capacitor maka φ = tan^-1(XC/R)
- e.g 
  - Sumber: 10 Volt, 1000 Hz.
  - Resistor (R): 100 Ohm.
  - Kapasitor (C): 2.2 µF
  - penyelesaian:
    - XC = 1/(2πfC) = 1/(2 x 3.14159 x 1000 x 0.0000022) = 72.34 Ohm
    - Z = sqrt(R^2 + XC^2) = sqrt(100^2 + 72.34^2) = 125.8 Ohm
    - I = Vs/Z = 10/125.8 = 0.081 A
    - Vr = I * R = 0.081 * 100 = 8.1 V
    - Vc = I * XC = 0.081 * 72.34 = 5.86 V
    - Vt = sqrt(Vr^2 + Vc^2) = sqrt(8.1^2 + 5.86^2) = 10 V
    - φ = tan^-1(XC/R) = tan^-1(72.34/100) = 35.9°
    - karena ini kapasitor maka ICE -> arus lebih dulu 35.9° dari tegangan sumber

### Perbedaan Simple DC dan AC
- Di Rangkaian DC (Baterai):
  - Pakai Resistansi (R).
  - Rumus: I = V/R
  - Hanya menghitung nilai.
- Di Rangkaian AC (PLN/Sinyal):
  - Kita pakai Impedansi (Z).
  - Rumus: I = V/Z
  - Menghitung nilai DAN waktu (fase).
