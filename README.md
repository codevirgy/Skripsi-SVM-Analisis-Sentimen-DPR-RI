# 🏛️ Implementasi Algoritma Support Vector Machine dalam Analisis Sentimen Kepercayaan Publik Terhadap Kinerja Dewan Perwakilan Rakyat Republik Indonesia

Repositori ini berisi *source code*, dataset, dan hasil komputasi visual untuk penelitian skripsi yang berfokus pada klasifikasi opini publik di media sosial X (Twitter) mengenai tingkat kepercayaan masyarakat terhadap kinerja Dewan Perwakilan Rakyat Republik Indonesia (DPR RI).

---

## 🎓 Informasi Akademis
* **Penulis:** Virgy Septiana
* **NPM:** 220660121104
* **Program Studi:** S1 Informatika
* **Fakultas:** Fakultas Teknologi Informasi
* **Institusi:** Universitas Sebelas April (UNSAP) Sumedang

---

## 📊 Hasil dan Performa Model

Model klasifikasi terbaik dibangun menggunakan algoritma **Support Vector Machine (SVM)** dengan fungsi **Kernel Radial Basis Function (RBF)** pada skenario pemotongan data latih dan uji **80:20**[cite: 4]. Konfigurasi parameter optimal (*hyperparameter tuning*) yang digunakan adalah `C = 10` dan `gamma = 0.1`

| Metrik Evaluasi | Nilai Capaian | Keterangan |
| :--- | :---: | :--- |
| **Accuracy** | 77,80% | Klasifikasi pola sentimen secara keseluruhan berpresisi tinggi. |
| **Precision** | 75,61% | Proporsi ketepatan prediksi pada data positif dan negatif sangat baik. |
| **Recall** | 77,80% | Sensitivitas mesin dalam mengenali kembali sentimen aktual cukup tangguh. |
| **F1-Score** | 76,63% | Nilai rata-rata harmonik stabil di tengah kondisi *imbalanced data*. |
| **10-Fold Cross Validation** | 79,78% | Model tervalidasi sangat stabil, konsisten, dan terhindar dari *overfitting*. |

### 📉 Distribusi Opini Publik Aktual
Berdasarkan ekstraksi otomatis (*lexicon-based*) menggunakan InSet Lexicon terhadap 4.972 korpus teks bersih (*clean text*), diperoleh pemetaan tingkat kepercayaan masyarakat sebagai berikut:
1. **Negatif:** 51,36% (2.568 Cuitan) - *Dominan*
2. **Positif:** 42,82% (2.141 Cuitan)
3. **Netral:** 5,82% (291 Cuitan)

### 🔠 Kontribusi Fitur Teks (*Top TF-IDF*)
Berikut adalah entitas kata yang memiliki signifikansi dan bobot tertinggi dalam membedakan polaritas opini antar dokumen cuitan (berdasarkan *Mean TF-IDF*):
1. `komisi` (0,0284)
2. `anggota` (0,0235)
3. `ketua` (0,0222)
4. `wakil` (0,0156)
5. `indonesia` (0,0155)

---

## 📂 Struktur Repositori

```text
📦 Skripsi-Sentimen-DPR-SVM
 ┣ 📂 Dataset
 ┃ ┣ 📜 01_dataset_raw.csv              # Data mentah hasil crawling dari platform X
 ┃ ┗ 📜 01_dataset_labeled.csv          # Data bersih dengan anotasi label InSet Lexicon
 ┣ 📂 Notebook
 ┃ ┗ 📜 Metode_SVM_Skripsi_Final.ipynb  # Source code utama (Preprocessing - Evaluasi)
 ┣ 📂 Visualisasi
 ┃ ┣ 📜 cm_rbf.png                      # Gambar Confusion Matrix skenario 80:20
 ┃ ┣ 📜 komparasi_kernel.png            # Bar chart komparasi 4 kernel SVM
 ┃ ┣ 📜 metrik_evaluasi.png             # Histogram performa akhir
 ┃ ┗ 📜 learning_curve.png              # Grafik evaluasi batas overfitting model
 ┗ 📜 README.md                         # Dokumentasi informasi repositori
