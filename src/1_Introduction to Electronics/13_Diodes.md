# Diodes

* untuk mengalirkan arus satu arah
* menjaga agar tidak terjadi arus balik (reverse bias) 
* e.g 
* ada battery 9V dan diode silicon (0.7V) maka diode akan butuh 0.7V untuk membuka gerbangnya agar arus bisa mengalir 
* hal tersebut disebut forward voltage drop (VF)
* diode butuh 0.7V untuk melewati barrier di P-N junction (forward bias)
* 0.7V ini asumsi untuk diode silicon
* karena asumsi maka VF harus dicek lagi di datasheet

* kalau voltage dari battery lebih kecil dari VF maka diode tidak akan mengalirkan arus

### jenis diode
* __standard diode (silicon diode)__ -> menggunakan P-N junction -> 1N4001
* __schottky diode__ -> hanya pakai N-type atau P-type bukan P-N junction, maka voltage drop-nya lebih kecil -> STPS2L60 
* __led__ -> kalau dilewati arus maka akan menghasilkan cahaya
* __zener diode (biasanya berwarna merah/orange)__ -> menjaga tegangan tetap stabil(akan menggunakan tegangan yang tertera di zener diode), bukan menyearahkan arus.

## circuit analysis dari AC ke DC
* listrik dari pln (AC 60Hz 110VAC) -> sinusoidal
* lalu di pasang transformers untuk step down ke 12VAC
* lalu di pasang rectifier (diode bridge (jadi satu arah)) untuk mengubah menjadi DC, keluar + dan - -> menjadi satu arah tapi belum stabil
    * bridge rectifier -> yaitu 4 diode yang dihubungkan bisa schottky maupun silicon
* lalu di pasang capacitor untuk mengurangi noise dan menjadi stabil tegangannya
* bisa di pasang inductor untuk mengurangi noise dan menjadi stabil arusnya
* ouputnya menjadi 12VDC

* karena sudah jadi 12VDC bisa dipasang diode (schottky) lalu bisa dimasukkan ke komponen elektronik lain 
* diode ini berfungsi ketika komponen elektronik tersebut downstream maka tidak akan mengalir arus ke arah yang tidak diinginkan (reverse bias(arus balik)) karena sudah ada diode

* kalau dipasangi zener diode 5.1V (positifnya dilewati rangkaiannya dan negatifnya langsung ke gnd) maka rangkaian yang melewati zener diode akan tetap stabil di 5.1V.

