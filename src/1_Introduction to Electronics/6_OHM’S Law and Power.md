# OHM’S Law and Power

## OHM’S Law
### voltage (V) = current (A) * resistance (Ω)
    * V = I * R
    * I = V / R
    * R = V / I

* e.g
    * V = 5V, R = 1kΩ   
    * maka I = V / R => 5V/1000Ω => 0.005A => 5 mA

## Power
### pada DC
* tegangan = tekanan air 
* arus = banyaknya air mengalir
* power = seberapa cepat air itu memutar turbin (kerja yang dilakukan) satuannya Watt .
### power (W) = voltage (V) × current (A)
    * P = V * I

* e.g
    * V = 5V, I = 5mA => 0.005A
    * P = V * I => 5V * 0.005A => 0.025 W => 25 x 10^3 W = 25 mW

### Elemen Menyerap atau Menghasilkan Daya
* Jika arus mengalir dari tegangan tinggi ke rendah, elemen menyerap daya (contoh: resistor).
* Jika arus mengalir dari tegangan rendah ke tinggi, elemen menghasilkan daya (contoh: baterai).

## Power
### pada AC
* Pada AC, tegangan & arus berbentuk gelombang sinus dan bisa tidak sefase (tidak naik-turun bersamaan).
* Power Factor (pf) = cos(θ)
    * Jika sefase → pf = 1 
    * Jika beda 90° → pf = 0 (tidak ada daya nyata!) 

* Power rata-rata AC:
    * P = Vrms * Irms * cos(θ)
        * dimana :
        * Vrms = Vpeak * 0.707
        * Irms = Ipeak * 0.707

# OHM'S Law Deep Dive

* P = V * I
* sedangkan I = V / R 
* maka P = V * (V / R) 
* maka P = V^2 / R

    * e.g
    * V = 9V, R = 10kΩ   
    * maka = I = V/R = 9/10000 = 0.0009 A = 0.9 mA
    * maka P = 81/10000 = 0.0081 W = 8.1 mW  

    * e.g
    * series circuit
    * 2 battery masing masing 1.5V maka V = 3V
    * 2 resistor masing-masing 100Ω dan 330Ω maka R = 430Ω
    * maka I = V/R = 3/430 = 0.006976 A = 6.976 mA
    * maka P = V * I = 3 * 0.006976 A = 20.928 mW
    * karena ada 2 resistor, dimana battery dibuat series berdekatan maka 
    * hitungan voltage setelah resistor 1 => V = I * R = 0.006976 A * 100Ω = 0.6976 V = 697.6 mV
    * hitungan voltage setelah resistor 2 => V = I * R = 0.006976 A * 330Ω = 2.30 V 
 