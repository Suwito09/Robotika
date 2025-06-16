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

# Ringkasan Pertemuan

## Pertemuan 1
### Pengantar Mata Kuliah Robotik
Di pertemuan perdana, kami mengikuti sesi perkenalan dengan dosen pengampu, Bapak Basuki Rahmat. Selanjutnya diperkenalkan gambaran umum bidang robotik, termasuk skema perkuliahan, ketentuan tugas UTS, serta rencana pelaksanaan UAS yang akan ditempuh sepanjang mata kuliah ini.

## Pertemuan 2
### Instalasi dan Persiapan Arduino IDE
Pada pertemuan kedua, fokus belajar beralih pada pemasangan Arduino IDE sebagai software utama untuk pemrograman mikrokontroler. Kami juga mempelajari cara menambahkan library–library penting dan melakukan konfigurasi dasar yang dibutuhkan pada IDE.

## Pertemuan 3
###Praktik Awal Arduino IDE dengan ITCLab
Di pertemuan ketiga, kami langsung mencoba menjalankan kode contoh dari Pak Basuki. Program tersebut mengendalikan mesin ITCLab untuk memutar “gerigi” dengan kecepatan yang dipercepat, lalu diperlambat hingga berhenti. Kegiatan ini memperkenalkan dasar pengaturan kecepatan motor melalui pemrograman.

## Pertemuan 4
### Mengoperasikan LED menggunakan Arduino IDE dan ITCLab
Pada pertemuan keempat, kami praktik menyalakan dan mematikan LED dengan kode yang tersedia. Materi utamanya adalah memahami penggunaan pin digital pada Arduino dan proses upload program ke board lewat ITCLab.

## Pertemuan 5
### Kontrol Motor dengan IMCLab
Pembelajaran dilanjutkan dengan praktik kendali motor melalui IMCLab. Kami mendalami penggunaan pin PWM serta prinsip dasar menggerakkan motor dengan mikrokontroler menggunakan Arduino IDE.

## Pertemuan 6
### Pengenalan IoT dan Aplikasi MQTT Panel
Materi pada pertemuan keenam beralih ke konsep Internet of Things (IoT). Kami diminta memasang aplikasi MQTT Panel di smartphone, kemudian belajar menghubungkan Arduino IDE dengan protokol MQTT via library PubSubClient. Untuk medium jaringan, digunakan hotspot smartphone dengan memasukkan SSID dan kata sandi ke dalam kode.

## Pertemuan 7
### Praktik Kontrol Robot BNU V2 via IoT MQTT Panel
Di pertemuan ketujuh, kami mengendalikan robot BNU V2 secara langsung melalui aplikasi MQTT Panel. Perintah dikirim lewat protokol MQTT dan diinterpretasikan menjadi aksi nyata pada robot, sehingga kami memperoleh pengalaman praktis komunikasi IoT dengan robotika.

# 🧠 Final Project

## 👥 Kelompok Peneliti

| Nama                | NIM         |
| ------------------- | ----------- |
| Yudhistira Nanda K. | 22081010055 |
| Daniel Perdana M.   | 22081010064 |
| Ferry Hasan         | 22081010085 |
| Suwito              | 22081010102 |
| Jerry Ramadhani C.  | 22081010140 |

---

## 📌 Deskripsi Singkat Proyek

Proyek ini bertujuan untuk membangun model klasifikasi gambar berbasis CNN (Convolutional Neural Network) untuk mengidentifikasi objek: **Kursi**, **Meja**, **Pintu**, dan **Manusia**.

---

## 🔍 Metodologi Penelitian

1. **Dataset**  
   Dataset berisi gambar 4 kelas: Kursi, Meja, Pintu, dan Manusia.  
   📁 _Jumlah data per kelas_: 40 gambar validasi dan 40 gambar test per kelas.  
   🔗 **Link dataset**: [Dataset di Google Drive / Kaggle](#)

2. **Arsitektur Model**

   - Transfer Learning menggunakan arsitektur pretrained seperti VGG16/VGG19
   - Fully Connected Layers di akhir untuk klasifikasi 4 kelas
   - Fungsi aktivasi: ReLU dan Softmax

3. **Training Setup**
   - Epoch: 20
   - Optimizer: Adam
   - Loss Function: Categorical Crossentropy
   - Batch size: disesuaikan dengan resource

---

## 📈 Proses Training Model

Berdasarkan **gambar Epoch logs dan grafik**:

- **Accuracy dan Loss** selama training terlihat sangat tinggi di data training dan juga validasi (akurasi validasi mencapai ~99.37% pada epoch ke-20).
- Namun terjadi indikasi **overfitting** karena model terlalu akurat pada data training dan validasi, tapi performa pada test dan klasifikasi per kelas buruk.

#### Gambar Grafik Akurasi & Loss:

- Kiri: Akurasi training dan validasi naik drastis
- Kanan: Loss training turun tajam, sementara **loss validasi naik** setelah beberapa epoch → indikasi overfitting.

---

## ✅ Evaluasi Model

### 📋 Classification Report (Validasi)

| Class   | Precision | Recall | F1-Score |
| ------- | --------- | ------ | -------- |
| Kursi   | 0.17      | 0.17   | 0.17     |
| Manusia | 0.22      | 0.23   | 0.22     |
| Meja    | 0.23      | 0.23   | 0.23     |
| Pintu   | 0.23      | 0.23   | 0.23     |

> **Accuracy hanya 21% pada data validasi meski akurasi sistem menunjukkan 99.37% → Overfitting parah.**

### 🧾 Confusion Matrix (Validasi)

![Confusion Matrix](path_to_confusion_matrix.png)

- Klasifikasi sangat tidak akurat, hampir semua kelas saling tertukar.
- Contoh: Gambar “Manusia” banyak diklasifikasikan sebagai “Kursi”.

### 🧪 Evaluasi Test Data

- **Test Accuracy**: 96.88%
- **Test Loss**: 0.4101

> Namun sama seperti validasi, akurasi tinggi ini menyesatkan karena model kemungkinan besar hanya hafal data training.

## 📂 Struktur Proyek

```
├── model/
│   └── saved_model.h5
├── notebooks/
│   └── model_training.ipynb
├── evaluation/
│   ├── confusion_matrix.png
│   └── training_graphs.png
└── README.md
```

---
