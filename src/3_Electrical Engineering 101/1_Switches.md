# Switches

* itu seperti tombol
* Normally Open (NO): Kondisi normalnya putus (OFF). Harus ditekan agar nyambung. (kondisi default open circuit ketika dipencet menjadi close circuit)
* Normally Closed (NC): Kondisi normalnya nyambung (ON). Harus ditekan agar putus. (kondisi default close circuit ketika dipencet menjadi open circuit)

### jenis switch
* momentary switch
* slide switch
* dip switch
* rotary switch

### trivia
* pahami berapa current yang bisa dihandle oleh switch agar switch tidak rusak
* switch yang dihubungkan ke microcontroller harus ada pull up atau pull down resistor agar microcontroller tidak bingung (floating) apakah ditekan atau tidak. tapi pada esp32 tidak perlu ada pull up atau pull down resistor karena esp32 sudah ada pull up atau pull down resistor di dalamnya dengan menggunakan code pinMode(pin_tombol, INPUT_PULLUP);