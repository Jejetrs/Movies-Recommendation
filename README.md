# 🎬 Movie Recommendation System - Hybrid Model Approach

Sistem rekomendasi film ini dikembangkan untuk membantu pengguna platform streaming dalam mengatasi **choice overload**, yaitu kebingungan dalam memilih tontonan karena terlalu banyak pilihan. Proyek ini menggunakan pendekatan **Content-Based Filtering**, **Collaborative Filtering**, dan **Hybrid** untuk menghasilkan rekomendasi yang **relevan**, **beragam**, dan **mencakup film kurang populer**.

---

## 📌 Tujuan Proyek

- Memberikan rekomendasi film yang sesuai dengan preferensi pengguna.
- Menghadirkan film baru yang belum pernah ditonton (novelty).
- Menyajikan rekomendasi yang tidak homogen dan lebih beragam (diversity).
- Memperluas cakupan rekomendasi ke film-film yang kurang dikenal (coverage).

---

## 🧠 Pendekatan Model

| Model                   | Deskripsi                                                                 |
|------------------------|---------------------------------------------------------------------------|
| 🎯 Content-Based       | TF-IDF + Cosine Similarity dari genre dan judul film.                     |
| 🤝 Collaborative       | RecommenderNet berbasis embedding neural network (TensorFlow).            |
| 🔀 Hybrid              | Skor gabungan dari CBF & CF, dengan penalti popularitas dan reranking.   |

---

## 📊 Hasil Evaluasi Model

| Model   | Mean Similarity (ILS) ↓ | Diversity ↑     | Coverage ↑       |
|---------|--------------------------|------------------|-------------------|
| CBF     | 0.1261 ❌                | 0.8739 ❌         | ✅ 0.7428         |
| CF      | ✅ 0.0232               | ✅ 0.9768        | 0.5281 ❌         |
| Hybrid  | ⚖️ 0.0909              | ⚖️ 0.9091       | ✅ 0.7457         |

> ✅ **Hybrid Model adalah solusi optimal**, menggabungkan kekuatan personalisasi dari CF dan jangkauan eksploratif dari CBF.

---

## 🔍 Dataset

- Sumber: [MovieLens 25M Dataset](https://www.kaggle.com/datasets/parasharmanas/movie-recommendation-system)
- Jumlah Film: 62.000+
- Jumlah Rating: 25.000.000+
- Fitur utama: `userId`, `movieId`, `rating`, `genres`, `title`

---

## 📂 Struktur Folder Proyek
```
movie-recommendation/
├── data/ # Dataset MovieLens
├── notebooks/ # Notebook eksplorasi & modeling
├── models/ # File model terlatih (.h5 / .pkl)
├── utils/ # Fungsi bantu (evaluasi, preproses, penalti, rerank)
├── app/ # Aplikasi Streamlit (opsional)
└── README.md
```
---
🧠 Insight Bisnis
- Hybrid model dapat mengatasi kelemahan masing-masing pendekatan individual.
- Memungkinkan eksplorasi konten long-tail yang jarang terekspos oleh sistem tradisional.
- Memberikan pengalaman eksplorasi film yang lebih personal, menarik, dan tidak repetitif.
