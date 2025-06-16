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
