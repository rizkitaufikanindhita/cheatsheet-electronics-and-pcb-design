# 5V Power Supply menggunakan 7805

- 7805 itu masuk linear regulator
- 7805 memakan voltage (voltage drop) sebanyak 2V, maka input minimal 7V kalau outputnya mau 5V

### Resep
- resep "Minimalis tapi Stabil" tinggal pakai ini saja:
    - IC 7805 (Jantungnya).
    - 4 Buah Kapasitor (2 di Input, 2 di Output).

### Rangkaian
- Input dan Output dari 7805
    - Kapasitor Besar (10µF - Elektrolit/Tantalum): Ini adalah "Tangki Cadangan". Menangani lonjakan arus besar yang lambat (frekuensi rendah).
    - Kapasitor Kecil (0.1µF - Keramik): Ini adalah "Filter Halus". Menangani noise frekuensi tinggi yang sangat cepat.
    - Posisi: Wajib sedekat mungkin dengan kaki IC regulator (7805).
