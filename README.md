# 🤖 Robotika Learning Repository - Kegiatan Perkuliahan

Selamat datang di repositori ini! Repository ini dibuat sebagai dokumentasi dan penyimpanan progres belajar penulis dalam bidang **ROBOTIKA**, baik dalam bentuk source code, catatan eksperimen.

## Pertemuan Pertama
[Perkenalan Mata Kuliah Robotik]
Pada pertemuan pertama mata kuliah robotik, seperti kegiatan awal pertemuan seperti umumnya yakni berkenalan. Mulai dari berkenalan dengan dosen pengampu, yakni Pak Basuki, kemudian dilanjut dengan berkenalan atau meraba sedikit tentang robotik. Pada tahap ini, kami menerima penjelasan mengenai apa saja yang akan dilakukan pada mata kuliah robotik ini, seperti bagaimana skema pembelajarannya, pengerjaan UTS, hingga pengerjaan UAS.

## Pertemuan Kedua
[Instalasi Arduino IDE]
Pada pertemuan kedua mata kuliah robotik, kegiatan pembelajaran difokuskan pada pengenalan dan instalasi Arduino IDE sebagai platform utama dalam pemrograman mikrokontroler. Selain itu, kami juga mempelajari bagaimana cara melakukan instalasi beberapa library penting yang akan digunakan dalam pengerjaan project pada mata kuliah robotik, serta bagaimana konfigurasi beberapa setup yang diperlukan.

## Pertemuan Ketiga
[Praktik Arduino IDE dengan ITCLab]
Pada pertemuan keempat mata kuliah robotik, diisi dengan praktik langsung menggunakan ITCLab, Disini kami mencoba untuk melakukan running program yang telah disediakan untuk menghidupkan dan mematikan LED. Pertemuan ini berfokus pada pemahaman konsep dasar pin digital pada Arduino IDE serta proses upload program ke board melalui ITCLab.

## Pertemuan Keempat
[Praktik Arduino IDE Dengan IMCLab]
Pada pertemuan ketiga mata kuliah robotik, kami mencoba melakukan running program yang disediakan oleh Pak Basuki, yakni menghidupkan mesin pada ITCLab, yang di mana mesin tersebut nanti akan diaktifkan, ketika sudah aktif, mesin tersebut akan memutar "gerigi" yang telah dikonfigurasi dari cepat ke lambat. Jadi ketika awal dinyalakan, "gerigi" tersebut akan berputar secara cepat, kemudian semakin melambat, dan berhenti.

## Pertemuan Kelima
[Kontrol Motor Dengan IMCLab]
Pada pertemuan kelima mata kuliah robotik, pembelajaran lanjut menggunakan IMCLab. Disini, kami mencoba mengendalikan motor dengan konfigurasi perintah dari Arduino IDE. Praktik pada pertemuan ini bertujuan untuk mengenal bagaimana penggunaan pin PWM dan dasar-dasar kendali penggerak melalui mikrokontroler.

## Pertemuan Keenam
[Pengenalan IoT dan MQTT Panel]
Pada pertemuan keenam mata kuliah robotik, pembelajaran masuk ke konsep Internet of Things (IoT), disini kami diarahkan untuk menginstal aplikasi IoT MQTT Panel di handphone. Kemudian, kami belajar menghubungkan Arduino IDE ke MQTT dengan bantuan library PubSubClient, sehingga Arduino IDE dapat berkomunikasi melalui jaringan internet. Dalam konfigurasinya, diperlukan sebuah hotspot dari handphone, kemudian memasukkan value nama hotspot beserta passwordnya pada sebuah kode dalam Arduino IDE.

## Pertemuan Ketujuh
[Praktik Kontrol Robot BNU V2 Via IoT MQTT Panel]
Pada pertemuan ketujuh mata kuliah robotik, kami mencoba mengendalikan robot BNU V2 dengan menggunakan aplikasi IoT MQTT Panel. Disini, kami mengirimkan sebuah perintah melalui MQTT Panel yang diterjemahkan menjadi aksi pada robot secara real-time. Praktik ini bertujuan untuk memahami penerapan praktis tentang komunikasi IoT menggunakan protokol MQTT.

---

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
