# UAS Machine Learning Project: Analisis Perbandingan Algoritma Random Forest Regression, dan XGBoost untuk Prediksi Daya Panel Surya Berdasarkan Data Meteorologi pada Wilayah 3T  di Indonesia

Proyek ini bertujuan untuk memprediksi output daya listrik panel surya di berbagai wilayah 3T (Terdepan, Terluar, Tertinggal) di Indonesia berdasarkan data meteorologi. Kami membandingkan performa dua algoritma machine learning: Random Forest Regression, dan XGBoost untuk menentukan model yang paling akurat dan efisien.

## Proyek

**Judul**: Analisis Perbandingan Algoritma Random Forest Regression, dan XGBoost untuk Prediksi Daya Panel Surya Berdasarkan Data Meteorologi pada Wilayah 3T  di Indonesia
**Topik**: Energi
**Rumusan Masalah**: 3.8 Minimnya Pemanfaatan IoT dan AI untuk Ekspansi Elektrifikasi di Daerah 3T

**Anggota Tim (Kelompok 4 - 2024C)**:

1. Rafael Hartono(23031554166)
2. Athiyyatus Salisah (24031554223)
3. Nurul Aini (24031554060)

## Rumusan Masalah

1. Bagaimana membangun model yang mampu mengestimasi potensi daya panel surya pada wilayah 3T berdasarkan data meteorologi sebelum panel surya dipasang?
2. Faktor meteorologi apa saja yang paling berpengaruh terhadap estimasi daya panel surya pada wilayah 3T?
3. Bagaimana perbandingan kinerja algoritma Random Forest Regression dan XGBoost dalam mengestimasi daya panel surya berdasarkan data meteorologi pada wilayah 3T?
4. Algoritma manakah yang memberikan performa terbaik dalam mengestimasi daya panel surya pada wilayah 3T?


## Tujuan

1. Mengembangkan model estimasi daya panel surya pada wilayah 3T berdasarkan data meteorologi.
2. Mengidentifikasi faktor meteorologi yang paling berpengaruh terhadap daya panel surya.
3. Menganalisis dan membandingkan kinerja algoritma Random Forest Regression dan XGBoost dalam mengestimasi daya panel surya.
4. Menentukan algoritma dengan performa terbaik berdasarkan hasil evaluasi model.


## Alur        
1. **Scrapping Data** : Pengambilan data dari API PVGIS untuk Kota/Kabupaten 3T di Indonesia (2015-2020).

2. **Exploration Data** :
* Visualisasi Daya Listrik Harian
* Penghapusan Kolom Waktu
* Pengecekan NaN
* Distribusi data tiap kota
* Statistika Deskriptif
* Penghapusan kolom Int

3. **Spliting**
* Menentukan X dan y
* Pembagian data train dan data test 80:20

4. **Feature Engineering & Correlation** :
* Encode kolom city ke numerik
* Pair plot
* Pearson Correlation
* Anova
* PCA

5. **Modeling** :

* **Random Forest** : 
Menggunakan 50 pohon
Kedalaman maksimal 15
Minimal 10 leaf

* **XGBoost** :
* Menggunakan 100 pohon dengan learning rate 0.1 dan kedalaman pohon maksimal 6.

  
## Hasil Evaluasi (Ringkasan)

Model menunjukkan akurasi yang sangat tinggi dalam memprediksi output daya harian:

| **Model**         | **MAE** | **RMSE** | **R2 Score** |
| ----------------------- | ------------- | -------------- | ------------------ |
| **Random Forest** | 14.5         | 28.96          | 0.9759             |
| **XGBoost**       | 15.65         | 30.08          | 0.974             |

## Dependensi

Proyek ini membutuhkan library berikut:

**Bash**

```
pip install gdown pandas numpy seaborn matplotlib statsmodels scikit-learn xgboost joblib```

## Struktur Folder

**Plaintext**

```
/
├── UAS_ML_Kel_4_2024C_166_060_223.ipynb # Notebook
├── pvgis_indonesia_energy.csv # Dataset hasil scraping API
├── encoded_city.joblib # Encoding
├── pca_transformed.joblib # PCA
├── scaler_data.joblib # scaler
└── README.md                 # Dokumentasi proyek
```


*Proyek ini dibuat untuk keperluan akademik sebagai bagian dari tugas UAS Machine Learning untuk Kelompok 4 (2024C).*
