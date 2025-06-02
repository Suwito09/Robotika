# Praktek Menggunakan Arduino

##  iMcLab.ino
Sketch Arduino ini mendemonstrasikan dasar-dasar pengendalian arah dan kecepatan motor DC menggunakan PWM. 
Motor akan bergerak maju dan mundur secara bergantian dengan kecepatan penuh, berhenti di antaranya, dan meningkatkan kecepatan secara bertahap dalam kondisi tertentu.

## itclab-07.ino
Firmware Arduino ini digunakan untuk mengendalikan iTCLab Shield melalui perintah serial. 
Pengguna dapat mengatur output PWM untuk dua saluran (Q1 dan Q2) serta LED, dan membaca suhu dari dua sensor (T1 dan T2). 
Perintah dikirim melalui antarmuka serial dan sistem merespons dengan mengatur output atau mengirim data suhu. 
Termasuk logika keamanan yang akan mematikan output secara otomatis jika suhu sensor melebihi batas tertentu, serta mendukung perintah versi dan stop.

## pid.py
File Python ini mendefinisikan kelas iTCLab untuk mengelola komunikasi serial dengan perangkat Arduino dalam eksperimen kontrol suhu dan akuisisi data. 
Mendukung pembacaan suhu (T1 dan T2), pengendalian output (heater dan LED melalui PWM), penyimpanan data ke file teks, serta penanganan koneksi secara otomatis dengan deteksi port. 
Dirancang untuk digunakan dalam eksperimen robotika dan kontrol proses, menggunakan library pyserial dan numpy.


## MQTT-Based Temperature Control Sketch
Sketch ini dirancang untuk sistem pengendalian suhu dengan kemampuan pemantauan dan pengendalian jarak jauh berbasis MQTT.
