# Basic Circuit Analysis

* practice 1 : pakai battery 4.2V, 1 resistor 220Ω
    * buat gambar schematic
    * coba hitung arusnya (A) => 19.1 mA tapi realnya 16.8 mA
    * coba cek tegangan (V) => realnya 4.2 V

* practice 2 : 
    * buat gambar schematic dengan 2 momentory switch, 2 resistor 220Ω, 2 led 
    * rangkaian ditambah led (flat side itu negatif(katoda))
    * tambah tombol momentory switch
    * coba cek tegangan (V) masing masing karena kan terbagi, jadi dicek dulu untuk hitung arus => 2V dan 2V
    * arusnya masing masing => 9mA dan 9mA
    * led itu hanya bisa menerima arus 20mA-30mA

### Seri (1 resistor + 1 LED)
* Sumber: 3.7 V
* Rangkaian: 3.7 V → R 220Ω → LED → balik ke baterai
* Arus di seluruh rangkaian sama: 16.8 mA
* Tegangan 3.7 V terbagi:
    * sebagian di resistor
    * sebagian di LED
    * VR + VLED = 3.7 V

### Paralel (2 rangkaian yang masing² = 1 resistor + 1 LED)
* Setiap cabang bentuknya __sama persis seperti rangkaian seri__ di atas:
* Tiap cabang dapat tegangan penuh 3.7 V antara + dan GND
* Di dalam satu cabang, 3.7 V itu juga terbagi ke resistor dan LED, persis seperti kasus seri:
* arus per cabang = 16.8 mA
* Karena ada 2 cabang, arus total dari baterai:
    * Itotal = 16.8 mA + 16.8 mA = 33.6 mA

## Battery
* Battery ada tulisan 3.7V dan 3000mAh 
* tegangan battery 3.7V
* arus battery 3000mAh = 3A artinya battery bisa memberikan arus 3A selama 1 jam
* mAh = milliampere-hour