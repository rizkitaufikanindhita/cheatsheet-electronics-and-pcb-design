# Resistors
* resistor itu untuk menghambat arus 
* arus yang mengalir lewat resistor itu bisa dihitung dengan ohm's law

## Cara hitung resistor

### nilai per warna
* black -> 0
* brown -> 1
* red -> 2
* orange -> 3
* yellow -> 4
* green -> 5
* blue -> 6
* purple -> 7
* gray -> 8
* white -> 9

### multiplier per warna 
* black -> 1
* brown -> 10
* red -> 100
* orange -> 1000 (1K)
* yellow -> 10000 (10K)
* green -> 100000 (100K)
* blue -> 1000000 (1M)
* purple -> 10000000 (10M)
* gray -> 100000000 (100M)
* white -> 1000000000 (1G)
* gold -> 0.1
* silver -> 0.01

### tolerance per warna
* brown -> 1%
* red -> 2%
* orange -> 0.05%
* yellow -> 0.02%
* green -> 0.5%
* blue -> 0.25%
* purple -> 0.1%
* gray -> 0.01%
* gold -> 5%
* silver -> 10%

### latihan hitung
* e.g brown black brown gold
* ada 4 strip kan 
* strip 1 -> brown -> nilai 1
* strip 2 -> black -> nilai 0
* multiplier -> brown -> 10
* tolerance -> gold -> 5% tolerance
* maka 10 * 10 => 100Ω nilai resistornya dengan 5% tolerance

__resistor itu menghambat arus bukan makan voltase (kayak dioda) yang digunakan untuk menghitung arus__
__jadi kalau ada rangkaian yang digunakan untuk hitung arus yaitu voltase terakhir setelah dikurangi voltase yang dimakan oleh dioda__

* potentiometer 
    * sejenis resistor yang bisa diatur dengan dialnya

* series and parallel resistor
    * series -> hambatannya diakumulasikan 
        * Rt = R1 + R2 + R3 + ... 
    * parallel -> hambatannya disederhanakan menjadi seperti series
        * Rt = R1 * R2 / (R1 + R2)