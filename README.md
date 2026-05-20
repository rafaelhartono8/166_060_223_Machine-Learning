# 166_060_223_Machine-Learning-Project

# UAS Machine Learning Project: Analisis Perbandingan Algoritma Random Forest Regression, XGBoost, dan LSTM untuk Prediksi Daya Panel Surya Berdasarkan Data Meteorologi pada Wilayah 3T  di Indonesia

Proyek ini bertujuan untuk memprediksi output daya listrik panel surya di berbagai wilayah 3T (Terdepan, Terluar, Tertinggal) di Indonesia berdasarkan data meteorologi. Kami membandingkan performa tiga algoritma machine learning: Random Forest Regression, XGBoost, dan LSTM (Long Short-Term Memory) untuk menentukan model yang paling akurat dan efisien.

## Proyek

**Judul**: Analisis Perbandingan Algoritma Random Forest Regression, XGBoost, dan LSTM untuk Prediksi Daya Panel Surya Berdasarkan Data Meteorologi pada Wilayah 3T  di Indonesia
**Topik**: Energi
**Rumusan Masalah**: 3.8 Minimnya Pemanfaatan IoT dan AI untuk Ekspansi Elektrifikasi di Daerah 3T

**Anggota Tim (Kelompok 4 - 2024C)**:

1. Rafael Hartono(23031554166)
2. Athiyyatus Salisah (24031554223)
3. Nurul Aini (24031554060)

## Tujuan

1. Menganalisis korelasi antara variabel meteorologi khas iklim tropis Indonesia terhadap output daya listrik panel surya.
2. Membangun dan menguji model prediksi menggunakan algoritma Random Forest dan XGBoost.
3. Membandingkan performa kedua algoritma dengan  evaluasi regresi untuk menemukan akurasi terbaik.
4. Mengevaluasi efisiensi komputasi training time dan penggunaan sumber daya dari masing-masing model untuk menentukan algoritma yang paling layak diimplementasikan.


1. **Data Acquisition** : Pengambilan data dari API PVGIS untuk berbagai koordinat di Indonesia (2015-2020).
2. **Preprocessing** :

* Pembersihan data dan penghapusan  *duplicate* .
* Konversi format waktu.
* Agregasi data dari per jam menjadi harian untuk mengurangi *sparsity* (nilai nol pada malam hari).

1. **Feature Engineering** :

* Penambahan *Lag Features* (t-1).
* Penambahan *Rolling Mean* (window 3 hari).

1. **Modeling** :

* **Random Forest** : Menggunakan 100 estimator.
* **XGBoost** : Menggunakan learning rate 0.1 dan max_depth 6.
* **LSTM** : Arsitektur 64 unit dengan aktivasi ReLU.

## Hasil Evaluasi (Ringkasan)

Model menunjukkan akurasi yang sangat tinggi dalam memprediksi output daya harian:

| **Model**         | **MAE** | **RMSE** | **R2 Score** |
| ----------------------- | ------------- | -------------- | ------------------ |
| **Random Forest** | 15.06         | 23.22          | 0.9997             |
| **XGBoost**       | 15.02         | 22.28          | 0.9997             |

## Dependensi

Proyek ini membutuhkan library berikut:

**Bash**

```
pip install pandas numpy seaborn matplotlib scikit-learn xgboost tensorflow
```

## Cara Penggunaan

1. Pastikan dataset `pvgis_indonesia_energy.csv` tersedia di direktori yang sama (dihasilkan oleh cell pertama pada notebook).
2. Jalankan notebook secara berurutan ( *run all* ) di Google Colab atau Jupyter Notebook.
3. Periksa visualisasi pada bagian distribusi data dan hasil evaluasi model.

## Struktur Folder

**Plaintext**

```
/
├── Copy_of_ML.ipynb          # Notebook utama analisis
├── pvgis_indonesia_energy.csv # Dataset hasil scraping API
└── README.md                 # Dokumentasi proyek
```

## Catatan

* Data memiliki *sparsity* sebesar 30.78% karena ketiadaan radiasi matahari pada malam hari. Hal ini diatasi dengan melakukan agregasi harian.
* Model LSTM memerlukan *reshaping* input menjadi 3D tensor (`[samples, time_steps, features]`).

*Proyek ini dibuat untuk keperluan akademik sebagai bagian dari tugas UAS Machine Learning untuk Kelompok 4 (2024C).*
