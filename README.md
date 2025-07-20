# Course Recommender System (Content-Based Filtering)

## 🎯 Tujuan Proyek
Membangun sistem rekomendasi sederhana berbasis konten (content-based filtering) untuk menyarankan kursus online yang relevan berdasarkan deskripsi kursus.

Sistem ini menggunakan data dari hasil scraping situs **Class Central** dengan web based scraping dengan beautifulsoup + selenium.

---

## 🛠️ Metodologi & Pendekatan

### 1. Text Vectorization: TF-IDF
Kami menggunakan metode **TF-IDF (Term Frequency-Inverse Document Frequency)** untuk mengubah data deskripsi teks menjadi vektor numerik yang bisa dibandingkan secara matematis.

Alasan menggunakan TF-IDF:
- Simpel dan cepat diterapkan
- Tidak membutuhkan pelatihan model seperti Word2Vec
- Cukup efektif untuk task pencocokan teks yang sederhana

### 2. Similarity Mapping: Cosine Similarity
Setelah teks dikonversi ke vektor, kami menghitung tingkat kemiripan antar kursus menggunakan **cosine similarity**. Metrik ini mengukur sudut antara dua vektor, dan tidak sensitif terhadap panjang dokumen.

---

## 🧠 Sistem Rekomendasi

Kami menyediakan **dua jenis pendekatan rekomendasi**:

1. **Berdasarkan Judul Kursus**  
   Sistem akan mengambil kursus yang sudah ada dalam dataset, lalu mencari kursus dengan deskripsi paling mirip.

2. **Berdasarkan Keyword Bebas**  
   Pengguna bisa memasukkan topik/kata kunci (misalnya: `"machine learning"`), dan sistem akan mencari kursus yang paling cocok dengan topik tersebut.

---

## 📊 Contoh Hasil Rekomendasi

Keyword: `"machine learning"`

| Judul Kursus | Deskripsi Singkat |
|--------------|-------------------|
| Machine Learning with Python | Dive into ML with Python, covering classification, regression... |
| Applied Machine Learning in Python | Learn practical ML using scikit-learn... |
| Mathematics for ML: Linear Algebra | Explore linear algebra fundamentals... |

---

## 🧩 Kendala dan Solusi

| Kendala | Solusi |
|--------|--------|
| Kolom `description` tidak dikenali | Melakukan pengecekan nama kolom dengan `df.columns` |
| `ModuleNotFoundError` saat import `sklearn` | Reinstall dan pastikan environment aktif |
| Judul tidak ditemukan saat rekomendasi | Ganti pendekatan dengan keyword-based |

---

## 📁 Struktur Folder
course-recommender/
│
├── classcentral_with_description.csv
├── similarity_matrix.csv
├── course_recommender.ipynb
├── README.md

https://github.com/maz720p