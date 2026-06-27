# 📚 PK-CASE-BASED
## Sistem Case-Based Reasoning (CBR) untuk Pencarian Putusan Pengadilan Menggunakan TF-IDF dan Cosine Similarity

Repository ini merupakan implementasi sistem **Case-Based Reasoning (CBR)** untuk melakukan pencarian kasus hukum yang memiliki tingkat kemiripan tinggi terhadap suatu kasus baru.

Metode yang digunakan pada penelitian ini adalah:

- Case-Based Reasoning (CBR)
- TF-IDF (Term Frequency – Inverse Document Frequency)
- Cosine Similarity
- Preprocessing Bahasa Indonesia menggunakan Sastrawi

Output sistem berupa daftar kasus yang paling relevan beserta rekomendasi solusi (amar putusan) berdasarkan kasus yang memiliki kemiripan tertinggi.

---

# 📂 Struktur Project

```
PK-CASE-BASED
│
├── data
│   ├── raw
│   │   ├── case_001.txt
│   │   ├── case_002.txt
│   │   └── ...
│   │
│   ├── processed
│   │   ├── cases.csv
│   │   ├── cases.json
│   │   ├── tfidf_vectorizer.pkl
│   │   └── tfidf_matrix.pkl
│   │
│   ├── eval
│   │   ├── queries.json
│   │   ├── retrieval_metrics.csv
│   │   ├── retrieval_distribution.png
│   │   └── retrieval_metrics_chart.png
│   │
│   └── results
│       └── predictions.csv
│
├── logs
│   ├── cleaning.log
│   └── extraction_stats.csv
│
├── data
│   ├── putusan_001.pdf
│   ├── putusan_002.pdf
│   └── ...
│
├── main.ipynb
└── README.md
```

---

# 🛠️ Library yang Digunakan

Project ini menggunakan beberapa library berikut:

- pdfplumber
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- Sastrawi

Semua library telah diinstal melalui notebook sehingga tidak diperlukan instalasi tambahan apabila notebook dijalankan dari awal.

---

# 🚀 Menjalankan Project

Project ini dibuat menggunakan **Jupyter Notebook**.

Untuk menjalankan seluruh pipeline cukup:

1. Buka file

```
main.ipynb
```

2. Jalankan notebook dari awal hingga akhir menggunakan

```
Run All Cells
```

Notebook akan menjalankan seluruh tahapan secara otomatis.

---

# 📌 Alur Pipeline

Pipeline terdiri dari empat tahapan utama.

## Tahap 1 — PDF Extraction

Melakukan ekstraksi seluruh dokumen PDF menjadi file teks (.txt).

Output:

```
data/raw/
```

---

## Tahap 2 — Case Base Construction

Melakukan preprocessing dokumen meliputi:

- cleaning OCR
- menghapus watermark
- menghapus header dan footer
- normalisasi teks
- ekstraksi metadata
- ekstraksi fitur

Output:

```
cases.csv
cases.json
```

---

## Tahap 3 — Case Retrieval

Tahapan ini melakukan:

- preprocessing Bahasa Indonesia
- stemming menggunakan Sastrawi
- pembentukan TF-IDF
- perhitungan Cosine Similarity
- pencarian Top-K kasus paling mirip

Output:

```
tfidf_vectorizer.pkl
tfidf_matrix.pkl
queries.json
```

---

## Tahap 4 — Case Solution Reuse

Tahapan ini menggunakan hasil retrieval untuk memberikan rekomendasi solusi berdasarkan kasus yang memiliki tingkat kemiripan tertinggi.

Output:

```
predictions.csv
```

---

# 📊 Output Project

Project akan menghasilkan beberapa file penting.

| File | Deskripsi |
|-------|-----------|
| cases.csv | Dataset hasil preprocessing |
| cases.json | Dataset format JSON |
| tfidf_vectorizer.pkl | Model TF-IDF |
| tfidf_matrix.pkl | Matrix TF-IDF |
| queries.json | Query evaluasi |
| retrieval_metrics.csv | Hasil evaluasi retrieval |
| predictions.csv | Hasil prediksi solusi |
| cleaning.log | Log preprocessing |

---

# 📖 Metode

Tahapan metode yang digunakan pada penelitian ini adalah sebagai berikut.

```
PDF Putusan
      │
      ▼
Ekstraksi Teks
      │
      ▼
Preprocessing
      │
      ▼
Case Base
      │
      ▼
TF-IDF Vectorization
      │
      ▼
Cosine Similarity
      │
      ▼
Top-K Retrieval
      │
      ▼
Case Solution Reuse
      │
      ▼
Prediksi Amar Putusan
```

---

# 📄 Dataset

Dataset yang digunakan berupa dokumen putusan pengadilan dalam format PDF yang diperoleh dari Direktori Putusan Mahkamah Agung Republik Indonesia.

---

# 👨‍💻 Author

Project ini dikembangkan sebagai implementasi tugas **Case-Based Reasoning (CBR)** menggunakan Python.