# Voltage Divider in DC

* untuk menurunkan tegangan dengan menggunakan 2 resistor yang dipasang seri (resistor kedua disebut resistor divider)
* Voltage Divider -> 
    * bisa untuk AC maupun DC
    * tidak untuk beban berat
    * menghubungkan sensor 5V ke pin input ESP32 (3.3V) agar ESP32 tidak rusak
* Transformer -> 
    * hanya untuk AC
    * untuk menyalakan komponen yang butuh arus besar 
    * menyalakan motor DC 5V dari sumber 12V. Jika pakai voltage divider, resistor akan panas sekali dan tegangannya akan drop saat motor berputar. Anda butuh penurun tegangan khusus (__Buck Converter__ untuk DC, atau __Trafo__ untuk AC).

### Rumus mencari Voltage pada spesifik resistor pada rangkaian voltage divider
* e.g ada 2 resistor
* V1 = Vin * (R1 / (R1 + R2)) -> V1 adalah tegangan pada resistor R1
* V2 = Vin * (R2 / (R1 + R2)) -> V2 adalah tegangan pada resistor R2

### Rumus Voltage Divider (img/3_Simple_Voltage_Divider.png)
![simple voltage divider](../img/3_Simple_Voltage_Divider.png)
* Vout = Vin * (R2 / (R1 + R2)) 
* R1 (Resistor Atas) -> Terhubung antara Sumber Tegangan (Vin) dan Output.
* R2 (Resistor Bawah) -> Terhubung antara Output dan GROUND (GND).
* Agar Voltage Divider bekerja akurat dan tegangan tidak "drop" saat dipakai maka Resistansi pada Beban harus minimal __10 KALI LIPAT__ lebih besar dari resistor pembagi tegangan (R2). Jika tidak, maka tegangan akan drop saat beban dipakai karena kan parallel maka akan dihitung Rtotal = (Rb * R2) / (Rb + R2). kalau Rb kecil maka Rtotal akan menjadi dibawah Resistor terkecil pada paralel tersebut yang menyebabkan Voutnya drop tidak sesuai hitungan awal. karena Rtotal ini akan menggantikan R2 yang seharusnya pada penentuan Vout.

__perlu diperhatikan arusnya karena kalau terlalu besar maka resistor akan panas dan bisa rusak__

__dalam pembuatan voltage divider lebih baik pakai fixed resistor daripada potentiometer__

![simulation simple voltage divider](../img/3_Simulation_Simple_Voltage_Divider.png)
