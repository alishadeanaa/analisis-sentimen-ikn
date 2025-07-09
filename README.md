# 🏗️ Analisis Sentimen Pembangunan IKN dengan KNN

Proyek ini bertujuan untuk menganalisis sentimen masyarakat terhadap pembangunan Ibu Kota Negara (IKN) menggunakan data dari Twitter dan algoritma K-Nearest Neighbors (KNN).

---

## 📚 Deskripsi Singkat

- **Sumber data**: Twitter (2086 tweet)
- **Pengambilan data**: Tweet Harvest via Twitter API
- **Fokus fitur**: `created_at`, `full_text`, dan `Label`
- **Data berlabel**: 586 tweet (manual labeling)
- **Data tidak berlabel**: 1500 tweet (diprediksi oleh model)
- **Preprocessing**: Normalisasi, cleaning, tokenisasi, stopwords removal, stemming
- **Feature engineering**: TF-IDF & Word2Vec (CBOW)
- **Modeling**: KNN + model pembanding lainnya

---

## 📆 Analisis Sentimen per Periode Pembangunan IKN

Pembangunan IKN dianalisis berdasarkan **empat periode utama**, untuk menggambarkan persepsi publik dari tahap awal hingga setelah pembangunan selesai. Setiap periode mencakup sentimen **positif**, **negatif**, dan **netral**.

> ⚠️ Persebaran data antar-periode tidak merata. Lonjakan data terjadi pada periode akhir akibat topik IKN ramai dibahas dalam debat capres saat pemilu.

| Periode                    | Positif | Negatif | Netral | Insight Dominan |
|---------------------------|---------|---------|--------|------------------|
| Sebelum Pembangunan       | 29      | 147     | 113    | 5 dari 10 orang tidak mendukung pembangunan IKN, menggambarkan kekhawatiran awal terhadap rencana dan pengumuman proyek. |
| Masa Pembangunan          | 10      | 296     | 34     | 9 dari 10 orang menunjukkan kekhawatiran, didominasi isu lingkungan dan sosial. |
| Akhir Pembangunan         | 635     | 397     | 87     | 6 dari 10 orang menunjukkan sentimen positif karena mulai terlihat hasil nyata pembangunan. |
| Setelah Pembangunan       | 55      | 59      | 152    | 5 dari 10 orang bersikap netral, mencerminkan sikap menunggu terhadap dampak jangka panjang IKN. |

### ✏️ Penjabaran Periode

- **🟠 Sebelum Pembangunan**: Fokus pada respons masyarakat terhadap rencana awal, pengumuman proyek, kajian kelayakan, dan perencanaan.  
- **🔵 Masa Pembangunan**: Menyoroti isu dampak lingkungan, konstruksi, dan keterlibatan masyarakat lokal.
- **🟢 Akhir Pembangunan**: Menganalisis ekspektasi masyarakat terhadap hasil proyek dan kesiapan infrastruktur.
- **⚪ Setelah Pembangunan**: Mengevaluasi reaksi terhadap operasional IKN dan dampaknya terhadap kehidupan masyarakat dan ekonomi regional.

---

## 🧠 Hasil Model Machine Learning

### 🔹 Akurasi Model dengan TF-IDF

| Model                  | Akurasi |
|------------------------|---------|
| KNN                    | **83.90%** |
| Random Forest          | 79.66% |
| XGBoost                | 79.66% |
| LightGBM               | 74.58% |
| CatBoost               | 74.58% |
| SVM                    | 73.73% |
| Naive Bayes Multinomial| 73.73% |

### 🔹 Akurasi Model dengan Word2Vec

| Model      | Akurasi |
|------------|---------|
| KNN        | 65.25%  |
| SVM        | 66.10%  |
| Random Forest | 60.17% |
| Naive Bayes Gauss | 46.61% |

✅ **KNN + TF-IDF + Manhattan distance** terbukti paling efektif untuk analisis sentimen ini.

