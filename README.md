### Proyek Analisis Sentimen Kebijakan Efisiensi Energi Pemerintah Indonesia Menggunakan Support Vector Machine dan Multinomial Naive Bayes

## 📌 Tentang Proyek

Proyek ini merupakan analisis sentimen terhadap komentar pengguna TikTok mengenai kebijakan efisiensi energi pemerintah Indonesia. Data yang digunakan diambil melalui proses scraping TikTok menggunakan Apify.

Penelitian ini bertujuan untuk mengidentifikasi kecenderungan opini masyarakat ke dalam tiga kategori sentimen, yaitu positif, negatif, dan netral, serta membandingkan kinerja dua algoritma klasifikasi machine learning, yaitu Support Vector Machine (SVM) dan Naive Bayes Classifier (NBC). Algoritma NBC menggunakan pendekatan Multinomial Naive bayes (MNB).

## 🎯 Tujuan Analisis

- Mengidentifikasi kecenderungan sentimen masyarakat terhadap kebijakan efisiensi energi.
- Mengolah dan menganalisis data komentar TikTok menggunakan teknik Natural Language Processing (NLP).
- Membandingkan performa algoritma SVM dan MNB.
- Mengevaluasi pengaruh SMOTE terhadap penanganan ketidakseimbangan kelas.
- Menentukan model dengan performa klasifikasi terbaik berdasarkan Macro F1-Score.

## 📊 Dataset

Dataset diperoleh dari komentar TikTok pada konten akun berita yang membahas kebijakan efisiensi energi pemerintah Indonesia.

Informasi dataset:
- Jumlah data awal: 7.187 komentar.
- Jumlah data setelah preprocessing: 6.400 komentar.
- Periode pengumpulan: 20 Maret – 21 Juni 2026.
- Kategori sentimen: Positif, Negatif, dan Netral.

Dataset lengkap tidak disertakan dalam repository ini untuk menjaga privasi dan membatasi distribusi data penelitian.

## ⚙️ Metodologi

Proses analisis dilakukan melalui beberapa tahapan:

1. **Data Collection** – Pengumpulan komentar TikTok terkait kebijakan efisiensi energi.
2. **Data Preprocessing** – Cleaning, case folding, normalisasi, tokenisasi, stopword removal, dan stemming.
3. **Data Labeling** – Pelabelan sentimen menggunakan VADER dengan penyesuaian kamus InSet.
5. **Exploratory Data Analysis (EDA)** – Analisis distribusi sentimen dan visualisasi data.
6. **Feature Extraction** – Mengubah teks menjadi representasi numerik menggunakan TF-IDF.
7. **Class Imbalance Handling** – Menerapkan SMOTE pada data latih.
8. **Model Classification** – Menggunakan SVM dan Multinomial Naive Bayes.
9. **Model Evaluation** – Membandingkan performa model berdasarkan Accuracy, Precision, Recall, dan Macro F1-Score.

## 🤖 Algoritma yang Digunakan

**1. Support Vector Machine (SVM)**

Digunakan untuk mengklasifikasikan sentimen ke dalam tiga kategori dengan pendekatan One-Against-One (OAO) dan kernel linear.

**2. Multinomial Naive Bayes (MNB)**

Digunakan sebagai algoritma pembanding untuk klasifikasi teks berdasarkan probabilitas kemunculan fitur.

**3. Synthetic Minority Over-sampling Technique (SMOTE)**

Digunakan untuk menangani ketidakseimbangan distribusi kelas pada data pelatihan.

## 🛠️ Tools & Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- NLTK
- Sastrawi
- Matplotlib
- Seaborn

## 📈 Hasil dan Evaluasi Model

Evaluasi model dilakukan untuk membandingkan performa Support Vector Machine (SVM) dan Multinomial Naive Bayes (MNB), baik sebelum maupun setelah penerapan SMOTE.
Pengujian menggunakan beberapa skenario rasio pembagian data, yaitu 90:10, 80:20, dan 70:30, serta variasi random state 42,123 dan 999 untuk melihat konsistensi hasil model.

Metrik evaluasi yang digunakan meliputi:
- Accuracy
- Macro Precision
- Macro Recall
- Macro F1-Score
Macro F1-Score digunakan sebagai metrik utama untuk mengevaluasi kemampuan model dalam mengklasifikasikan setiap kategori sentimen.

### Perbandingan Hasil Evaluasi Tertinggi Seluruh Model

| Model | Rasio | Accuracy | Macro Precision | Macro Recall | Macro F1-Score |
|---|---|---:|---:|---:|---:|
| SVM | 90:10 | 0,88 | 0,84 | 0,83 | 0,84 |
| NBC (MNB) | 80:20 | 0,67 | 0,70 | 0,37 | 0,33 |
| SVM + SMOTE | 90:10 | **0,89** | **0,86** | **0,86** | **0,86** |
| NBC (MNB) + SMOTE | 80:20 | 0,68 | 0,58 | 0,62 | 0,59 |

### Analisis Hasil Evaluasi

Berdasarkan hasil perbandingan, model SVM dengan penerapan SMOTE memperoleh hasil evaluasi tertinggi dengan Accuracy sebesar 0,89 dan Macro F1-Score sebesar 0,86.
Penerapan SMOTE pada SVM meningkatkan Macro F1-Score dari 0,84 menjadi 0,86. Sementara itu, pada Multinomial Naive Bayes, Macro F1-Score meningkat dari 0,33 menjadi 0,59 setelah penerapan SMOTE.

Hasil tersebut menunjukkan bahwa SVM + SMOTE memberikan performa klasifikasi terbaik dibandingkan kombinasi model lainnya.

## 💡 Temuan 

Hasil analisis sentimen menunjukkan bahwa sentimen negatif mendominasi tanggapan masyarakat terhadap kebijakan efisiensi energi pemerintah Indonesia.
Beberapa kata yang sering muncul dalam sentimen negatif antara lain *tidak*, *bbm*, *wfh*, *liter*, *kerja*, dan *rakyat*.
Ini menggambarkan adanya tanggapan kritis masyarakat terhadap implementasi kebijakan efisiensi energi. Hasil penelitian dapat menjadi bahan evaluasi bagi pemerintah dalam meningkatkan sosialisasi, memperjelas informasi kebijakan, serta memperhatikan respons dan kebutuhan masyarakat.
