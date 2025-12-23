# 🚗 Vehicle Insurance Fraud Detection & Prevention

Proyek ini bertujuan untuk mengurangi kerugian finansial perusahaan asuransi secara proaktif dengan mendeteksi dan mencegah klaim asuransi kendaraan yang curang (fraud) sebelum disetujui.

---

## 📊 Ringkasan Proyek

- **Tujuan Utama:** Mendeteksi klaim asuransi palsu untuk meminimalkan biaya kerugian bisnis.
- **Gambaran Data:** Menggunakan dataset dari Kaggle (15.420 baris) dengan fokus pada fitur laporan polisi, suplemen, dan biaya deductible.
- **Masalah Utama:** Ketidakseimbangan kelas yang ekstrem, di mana hanya **5,99%** data merupakan kasus penipuan, sementara **94,01%** adalah klaim sah.
- **Hasil Terbaik:** Model **Expert-Based** berhasil memberikan dampak finansial nyata dengan **ROI sebesar 132,81%**.

---

## 📑 Daftar Isi

1. [Pemahaman Bisnis](#1-pemahaman-bisnis)
2. [Deskripsi Data](#12-data-description)
3. [Exploratory Data Analysis (EDA)](#2-exploratory-data-analysis)
4. [Evaluasi Model](#3-evaluasi-model)
5. [ROI & Dampak Bisnis](#4-roi--kalkulasi-keuntungan)
6. [Kesimpulan & Langkah Selanjutnya](#5-kesimpulan)

---

## 1. Pemahaman Bisnis

### 1.1 Tujuan Bisnis

Mengalihkan proses dari reaktif menjadi proaktif dalam menangani klaim bodong guna menghemat jutaan dolar biaya operasional.

### 1.2 Data Description

Kami memfokuskan analisis pada kolom-kolom kunci berikut:

| Fitur                   | Tipe        | Deskripsi                                                |
| :---------------------- | :---------- | :------------------------------------------------------- |
| **PoliceReportFiled**   | Binary      | Keberadaan laporan kepolisian resmi di lokasi kejadian.  |
| **NumberOfSuppliments** | Categorical | Jumlah pengajuan dana tambahan di luar estimasi awal.    |
| **Deductible**          | Numerical   | Beban biaya mandiri yang harus dibayar pemegang polis.   |
| **FraudFound_P**        | Binary      | **Target**: Indikator kecurangan (1) atau klaim sah (0). |

---

## 2. Exploratory Data Analysis (EDA)

Temuan kunci dari analisis data:

- **PoliceReportFiled:** Klaim tanpa laporan polisi (`No`) memiliki probabilitas penipuan yang lebih tinggi.
- **NumberOfSuppliments:** Klaim dengan sedikit dokumen tambahan (`none` atau `1-2`) secara kontraintuitif menunjukkan risiko fraud lebih tinggi.
- **Deductible:** Nilai 500 dikaitkan dengan probabilitas penipuan yang sedikit lebih tinggi.

---

## 3. Evaluasi Model

Kami membandingkan tiga pendekatan untuk mendeteksi penipuan:

| Model                | Recall (Deteksi Fraud) | Business Cost   | Keterangan                              |
| :------------------- | :--------------------- | :-------------- | :-------------------------------------- |
| **Naive (Baseline)** | 0%                     | \$6.800.000+    | Gagal mendeteksi penipuan sama sekali.  |
| **Expert-Based**     | **21,2%**              | **\$6.758.555** | **Terbaik**: Meminimalkan biaya bisnis. |
| **Statistics-Based** | Variatif               | Menengah        | Berdasarkan ambang batas IQR.           |

---

## 4. ROI & Kalkulasi Keuntungan

Model Expert-Based menunjukkan efisiensi finansial yang signifikan:

- **Total Utility:** Manfaat bersih dari prediksi benar dikurangi biaya prediksi salah.
- **Total Cost of Ownership (TCO):** \$30.000.
- **ROI:** **132,81%**.

Model ini tidak hanya mendeteksi penipuan, tetapi juga memastikan operasional tetap menguntungkan dengan mempertimbangkan biaya investigasi manual.

---

## 5. Kesimpulan

1.  **Integrasi Proaktif:** Model dapat diintegrasikan ke sistem klaim untuk memberikan bendera (_flag_) otomatis pada klaim berisiko tinggi.
2.  **Langkah Selanjutnya:** \* Transisi ke **Machine Learning dinamis** (Random Forest/XGBoost).
    - Penerapan teknik **SMOTE** untuk menangani ketidakseimbangan kelas secara lebih teknis.
    - Pengayaan data dengan fitur historis nasabah.

---
