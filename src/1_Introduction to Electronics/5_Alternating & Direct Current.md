# Alternating and Direct Current
### DC
Arus mengalir satu arah saja (dari + ke −) 
### AC
Arus bolak-balik (arahnya berubah terus seiring waktu)

# DC (Direct Current)
-	Arusnya tetap searah dan tegangannya konstan.
-	Contohnya: baterai, powerbank, lampu senter, alat elektronik kecil.
-   Nilai tegangan DC itu tidak bisa dibawah 0. kalau AC bisa dibawah 0.
-	Walau di dalam rangkaian digital tegangannya naik-turun karena switching, arah arusnya tetap sama, jadi tetap DC.
-	Ibarat air mengalir dari satu tangki tinggi ke tangki rendah — selalu satu arah. (+ ke -)
-   Voltase source symbol itu yang ada + dan – nya.

### VCVS (Voltage Controlled Voltage Source)
- tegangan keluarannya mengikuti atau bergantung pada tegangan input dengan penguatan tertentu.
- Vout = f(x) 
- Vout itu tegangan output yang ditentukan atau dipengaruhi oleh input x 

### CCVS (Current Controlled Voltage Source)
- tegangan keluarannya dikendalikan oleh arus
- Vout bergantung pada arus input

# AC (Alternating Current)
-	Tegangan dan arusnya naik-turun dan bolak-balik dari positif ke negatif.
-   biasanya berbentuk gelombang sinus.
-	Contohnya: listrik rumah dari stop kontak (PLN).
-	Arusnya berubah arah 60 kali per detik (60 Hz) di Amerika atau 50 Hz di banyak negara lain.
-	Ibarat air yang mengalir maju-mundur terus di pipa, bukan satu arah aja.
### Frekuensi (Hz)
- Supaya tahu seberapa cepat gelombang berubah.
- berubah arah 60 kali per detik kalau 60 Hz.
- Rumus: f = 1 / T
- (T = periode, waktu 1 siklus)
- Contoh: listrik rumah 50/60 Hz — penting untuk sinkronisasi alat elektronik.
### Peak dan Peak-to-Peak (Vp-p)
- Peak :
    - Vpmax = puncak positif
    - Vpmin = puncak negatif
    - Contoh: +5 V dan –3 V
- Peak-to-Peak:
    - Selisih antara puncak positif dan puncak negatif.
    - Rumus: Vp-p = Vpmax – Vpmin
    - Contoh: Vp-p = 5 – (–3) = 8 V
- Supaya tau seberapa tinggi tegangan bisa mencapai.
- Penting untuk:
    - memilih komponen agar tidak jebol akibat tegangan puncak yang terlalu besar
    - desain rangkaian yang aman
### RMS (Root Mean Square)
- Karena AC tidak konstan untuk menentukan V digunakan RMS agar sama dengan DC yang konstan
- contoh 120V atau 220V itu bukan peak tapi RMS yang digunakan sebagai nilai tegangan AC
- e.g untuk gelombang sinus
- Rumus: Vrms = 0.5 × Vp-p × 0.707

- Rumus Final: Vrms = Vp-p * 0.3535
- e.g kalau Vrms 120V maka Vp-p nya 339.6V
- kalau seimbang maka Vpmax = 169V, Vpmin = -169V
- Vrms itu nilai Voltase AC
#### Semua rangkaian digital (komputer, microcontroller, game console) pakai DC. Tapi sumber listriknya dari AC (PLN) → makanya butuh adaptor atau power supply buat ubah AC ke DC.


