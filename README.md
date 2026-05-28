# Final-Project-KAL-KELOMPOK-7-DATASET-CKD

# Klasifikasi Chronic Kidney Disease menggunakan HistGradientBoostingClassifier dengan Feature Selection SelectFromModel Berbasis Random Forest

Proyek ini merupakan implementasi pipeline machine learning untuk klasifikasi Chronic Kidney Disease (CKD) menggunakan dataset tabular medis dari Kaggle. Dataset memiliki 1.659 sampel, 54 kolom awal, 51 fitur prediktif setelah pembersihan dua kolom noise, terdiri dari 15 fitur biner/kategorikal dan 36 fitur kontinu/numerik. Dataset juga bersifat imbalanced dengan rasio kelas sekitar 11,3:1 dan tidak memiliki missing value. 

## Ringkasan Proyek

Tujuan utama proyek ini adalah membangun model klasifikasi CKD yang lebih stabil dan relevan secara klinis melalui tahapan EDA, preprocessing, feature selection, penanganan class imbalance, tuning hyperparameter, dan optimasi threshold. Feature selection dilakukan menggunakan SelectFromModel berbasis Random Forest untuk mempertahankan fitur-fitur yang paling berpengaruh, lalu klasifikasi akhir dibangun menggunakan HistGradientBoostingClassifier. 

## Alur Kerja

Pipeline proyek ini dimulai dari data cleaning, lalu dilanjutkan dengan Exploratory Data Analysis (EDA) untuk memahami distribusi kelas, statistik deskriptif, dan pola data. Setelah itu dilakukan penanganan outlier dengan IQR Capping pada 36 fitur numerik, normalisasi dengan StandardScaler, seleksi fitur, train-test split stratified, penanganan imbalance menggunakan sample_weight, tuning hyperparameter, threshold tuning, dan evaluasi model secara komprehensif. 

## Metode yang Digunakan

Feature selection dilakukan dengan RandomForestClassifier menggunakan `n_estimators=200`, `class_weight='balanced'`, dan `max_depth=10`. Threshold final dipilih pada nilai mean importance sebesar `0.01961`, sehingga jumlah fitur berkurang dari 51 menjadi 27 fitur terpilih. Pendekatan ini dipilih karena memberikan keseimbangan yang baik antara reduksi dimensi dan retensi informasi penting. 

Untuk klasifikasi, proyek ini menggunakan HistGradientBoostingClassifier dengan hasil tuning terbaik `learning_rate=0.2`, `max_iter=500`, `max_depth=None`, dan `l2_regularization=0.0`. Penanganan imbalance dilakukan menggunakan `sample_weight` dengan bobot sekitar `11.29` untuk kelas negatif dan `1.00` untuk kelas positif, sedangkan threshold optimal pada tahap evaluasi diperoleh di sekitar `0.93`. 

## Hasil dan Evaluasi

Evaluasi model dilakukan menggunakan berbagai metrik seperti Accuracy, Precision, Recall, F1-score, F1-macro, ROC-AUC, Average Precision, confusion matrix, ROC curve, PR curve, permutation importance, dan validation curve. Hasil akhir menunjukkan bahwa model mampu mempelajari pola CKD dengan baik, terutama setelah dilakukan balancing, seleksi fitur, dan optimasi threshold agar performa pada kelas minoritas menjadi lebih representatif. 

## Kesimpulan

Secara keseluruhan, proyek ini menunjukkan bahwa kombinasi preprocessing yang tepat, feature selection berbasis Random Forest, dan klasifikasi menggunakan HistGradientBoostingClassifier dapat digunakan untuk membangun model CKD yang lebih efisien, stabil, dan relevan secara medis. Pendekatan ini juga membantu mengurangi dimensi fitur tanpa mengorbankan fitur-fitur klinis yang penting seperti biomarker fungsi ginjal. 

---

## Anggota Kelompok

- Muhammad Fakhri Aldiansyah  
- Jason Manuel  
- Putri Griselda Sonandi
