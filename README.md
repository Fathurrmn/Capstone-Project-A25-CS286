# Capstone-Project-A25-CS286
# Customer Segmentation & Business Strategy Analysis

## 1. Deskripsi Singkat Proyek
Proyek ini adalah *end-to-end data science pipeline* yang bertujuan untuk mengidentifikasi segmen pelanggan dari data transaksi ritel dan merumuskan strategi bisnis yang dapat ditindaklanjuti.

Berbeda dengan pendekatan RFM standar, proyek ini menggunakan fitur perilaku berbasis **Volume (Total Quantity)**, **Nilai Transaksi (Avg Transaction Value)**, dan **Preferensi Harga (Avg Unit Price)** untuk menemukan pola belanja yang unik.

Alur proyek terdiri dari tiga tahapan utama:
1.  **Data Cleaning:** Membersihkan data transaksi mentah, membuang transaksi retur/negatif, dan menangani *outliers*.
2.  **Clustering (K-Means):** Mengelompokkan pelanggan menjadi 4 persona utama: *Big Spender, The Whales, Quality Seekers,* dan *Budget Shoppers*.
3.  **Business Simulation:** Menghitung potensi kenaikan pendapatan (*revenue uplift*) dengan menerapkan strategi promosi yang dipersonalisasi untuk setiap persona.

---

## 2. Petunjuk Setup Environment

Ikuti langkah-langkah berikut untuk menyiapkan lingkungan kerja lokal Anda agar kode dapat berjalan tanpa error.

### Prasyarat
- Python 3.8 atau lebih baru.
- Anaconda atau Virtualenv (disarankan).

### Langkah Instalasi
1.  **Clone Repository**
    ```bash
    git clone [https://github.com/username/customer-segmentation-project.git](https://github.com/username/customer-segmentation-project.git)
    cd customer-segmentation-project
    ```

2.  **Buat Virtual Environment**
    ```bash
    # Menggunakan venv
    python -m venv venv
    
    # Aktivasi (Windows)
    venv\Scripts\activate
    
    # Aktivasi (Mac/Linux)
    source venv/bin/activate
    ```

3.  **Install Dependencies**
    Pastikan file `requirements.txt` tersedia (berisi pandas, numpy, sklearn, matplotlib, seaborn, plotly).
    ```bash
    pip install -r requirements.txt
    ```

---

## 3. Tautan Model ML & Dataset

Proyek ini menghasilkan model K-Means dan dataset yang telah diproses. Anda dapat mengunduh atau memuat file berikut:

* **Dataset Bersih (Cleaned Data):**
    [Download Sales_Transaction_Cleaned.csv](./data/Sales_Transaction_Cleaned.csv)
    *(Output dari Sprint 1)*

* **Hasil Clustering (Customer Personas):**
    [Download Hasil_Clustering_Customer.csv](./data/Hasil_Clustering_Customer.csv)
    *(Output dari Sprint 2 & 3, digunakan sebagai input Sprint 4)*

* **Model K-Means (Pickle File - Opsional):**
    [Download kmeans_model.pkl](./models/kmeans_model.pkl)
    *(Gunakan `joblib.load()` atau `pickle.load()` untuk memuat model ini tanpa training ulang)*

---

## 4. Cara Menjalankan Aplikasi

Aplikasi ini berbentuk serangkaian Jupyter Notebook yang harus dijalankan secara berurutan untuk menjaga integritas data.

**Langkah 1: Data Cleaning**
* Buka file `Sprint_1_A25_CS286.ipynb`.
* Jalankan semua sel. Notebook ini akan memproses data mentah dan menghasilkan file `Sales_Transaction_Cleaned.csv`.

**Langkah 2: Modeling & Clustering**
* Buka file `Sprint_2_dan_3_A25_CS286.ipynb`.
* Pastikan file `Sales_Transaction_Cleaned.csv` berada di direktori yang sama.
* Jalankan notebook untuk melatih model K-Means. Output berupa file `Hasil_Clustering_Customer.csv` yang berisi label klaster setiap pelanggan.

**Langkah 3: Business Insight & Strategy**
* Buka file `Sprint_4_A25_CS286.ipynb`.
* Notebook ini akan memuat hasil klasterisasi, memetakan persona (misal: Cluster 0 -> Big Spender), dan memvisualisasikan simulasi bisnis.
* Gunakan slider atau parameter di dalam notebook untuk melihat proyeksi *revenue* berdasarkan skenario strategi yang berbeda.
