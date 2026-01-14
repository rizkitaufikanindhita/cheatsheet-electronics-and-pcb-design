# Transistor

- Intinya berfungsi
    - Switch -> Menghidupkan atau mematikan beban secara otomatis menggunakan arus/tegangan kecil.
    - Amplifier -> Menggunakan arus/tegangan kecil untuk meng-ON-kan beban yang butuh arus/tegangan lebih besar

### e.g Switch
![npn_motor](../../img/npn_motor.png)
- transistor NPN itu "Low-Side Switching" (Saklar Sisi Bawah(pada bagian negatif)) karena e.g menyalakan pompa dengan transistor NPN, power supply + dirangkai dengan kabel positif dari pompa, kabel negatif dari pompa masuk ke collector transistor, ditambah juga diode dengan kabel positif dari diode masuk ke collector transistor dan negatif masuk ke power supply +, dan emitter transistor dihubungkan ke GND, power supply juga dihubungkan dengan momentory switch lalu ke resistor dan dimasukkan ke base transistor

- Arus listrik (+) sebenarnya sudah standby masuk ke pompa, tapi dia macet tidak bisa mengalir karena jalan pulang ke Ground diputus oleh Transistor NPN di bawah. Begitu Anda tekan tombol, jalan ke Ground terbuka, arus mengalir, pompa nyala.

- Intinya (NPN Transistor) Arus dan tegangan dari Base itu untuk buka gerbang saja biar arus dari Collector bisa masuk ke Emitter (GND). Load jadi nyala. dan ada Resistor di Base agar gerbangnya (NPN Transistor) tidak didobrak terlalu keras (rusak).

