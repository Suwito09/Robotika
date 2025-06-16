# Praktek Menggunakan Arduino

##  iMcLab.ino
Sketch Arduino ini menunjukkan konsep dasar dalam mengontrol arah dan kecepatan motor DC menggunakan sinyal PWM. Motor akan bergerak maju dan mundur secara bergantian pada kecepatan maksimum, berhenti di antara perpindahan, serta melakukan akselerasi secara bertahap dalam kondisi tertentu.

## itclab-07.ino
Firmware ini memungkinkan kontrol iTCLab Shield melalui perintah yang dikirim lewat koneksi serial. Pengguna dapat mengatur keluaran PWM untuk dua kanal (Q1 dan Q2) serta LED, dan juga memantau suhu dari dua sensor (T1 dan T2). Perintah dikomunikasikan melalui antarmuka serial, dan sistem akan menanggapi dengan menyesuaikan output atau mengirimkan data suhu. Terdapat juga fitur keamanan otomatis yang mematikan output jika suhu melampaui ambang tertentu, serta dukungan untuk perintah versi dan penghentian.

## pid.py
Skrip Python ini mendefinisikan kelas iTCLab untuk menangani komunikasi serial antara komputer dan Arduino dalam eksperimen pengendalian suhu dan pencatatan data. Fungsinya mencakup pembacaan suhu (T1 dan T2), kontrol output (pemanas dan LED dengan PWM), penyimpanan data ke file teks, dan pendeteksian port otomatis. Skrip ini ditujukan untuk eksperimen dalam bidang robotika dan kontrol proses, menggunakan pustaka pyserial dan numpy.

## MQTT-Based Temperature Control Sketch
Sketch ini dikembangkan untuk sistem pengendalian suhu yang mendukung pemantauan dan kontrol dari jarak jauh menggunakan protokol MQTT.
