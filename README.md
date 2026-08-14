# 🏛️ Implementasi Algoritma Support Vector Machine dalam Analisis Sentimen Kepercayaan Publik Terhadap Kinerja Dewan Perwakilan Rakyat Republik Indonesia

Repositori ini berisi *source code*, dataset, dan hasil komputasi visual untuk penelitian skripsi yang berfokus pada klasifikasi opini publik di media sosial X (Twitter) mengenai tingkat kepercayaan masyarakat terhadap kinerja Dewan Perwakilan Rakyat Republik Indonesia (DPR RI)[cite: 2].

---

## 🎓 Informasi Akademis
* **Penulis:** Virgy Septiana[cite: 2]
* **NPM:** 220660121104[cite: 2]
* **Program Studi:** S1 Informatika[cite: 2]
* **Fakultas:** Fakultas Teknologi Informasi[cite: 2]
* **Institusi:** Universitas Sebelas April (UNSAP) Sumedang[cite: 2]

---

## 📊 Hasil dan Performa Model

Model klasifikasi terbaik dibangun menggunakan algoritma **Support Vector Machine (SVM)** dengan fungsi **Kernel Radial Basis Function (RBF)** pada skenario pemotongan data latih dan uji **80:20**[cite: 4]. Konfigurasi parameter optimal (*hyperparameter tuning*) yang digunakan adalah `C = 10` dan `gamma = 0.1`[cite: 4].

| Metrik Evaluasi | Nilai Capaian | Keterangan |
| :--- | :---: | :--- |
| **Accuracy** | 77,80% | Klasifikasi pola sentimen secara keseluruhan berpresisi tinggi[cite: 4]. |
| **Precision** | 75,61% | Proporsi ketepatan prediksi pada data positif dan negatif sangat baik[cite: 4]. |
| **Recall** | 77,80% | Sensitivitas mesin dalam mengenali kembali sentimen aktual cukup tangguh[cite: 4]. |
| **F1-Score** | 76,63% | Nilai rata-rata harmonik stabil di tengah kondisi *imbalanced data*[cite: 4]. |
| **10-Fold Cross Validation** | 79,78% | Model tervalidasi sangat stabil, konsisten, dan terhindar dari *overfitting*[cite: 4]. |

### 📉 Distribusi Opini Publik Aktual
Berdasarkan ekstraksi otomatis (*lexicon-based*) menggunakan InSet Lexicon terhadap 4.972 korpus teks bersih (*clean text*), diperoleh pemetaan tingkat kepercayaan masyarakat sebagai berikut[cite: 4]:
1. **Negatif:** 51,36% (2.568 Cuitan) - *Dominan*[cite: 4]
2. **Positif:** 42,82% (2.141 Cuitan)[cite: 4]
3. **Netral:** 5,82% (291 Cuitan)[cite: 4]

### 🔠 Kontribusi Fitur Teks (*Top TF-IDF*)
Berikut adalah entitas kata yang memiliki signifikansi dan bobot tertinggi dalam membedakan polaritas opini antar dokumen cuitan (berdasarkan *Mean TF-IDF*)[cite: 4]:
1. `komisi` (0,0284)[cite: 4]
2. `anggota` (0,0235)[cite: 4]
3. `ketua` (0,0222)[cite: 4]
4. `wakil` (0,0156)[cite: 4]
5. `indonesia` (0,0155)[cite: 4]

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
