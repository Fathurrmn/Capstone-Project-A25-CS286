# Capstone Project A25-CS286
# Analysis Customer Segmentation

## 👨‍💻 Project Team

- **Fathur Rahman**  
  *Universitas Gunadarma*

- **Dewa Bagus Putu Arya Dhananjaya**  
  *Universitas Gunadarma*

- **Afridho Tattaq Tavadhu**  
  *Universitas Stikubank*

---

## 1. Deskripsi Singkat Proyek
Proyek ini adalah *end-to-end data science pipeline* yang bertujuan untuk mengidentifikasi segmen pelanggan dari data transaksi ritel dan merumuskan strategi bisnis yang dapat ditindaklanjuti.

Berbeda dengan pendekatan RFM standar, proyek ini menggunakan fitur perilaku berbasis **Volume (Total Quantity)**, **Nilai Transaksi (Avg Transaction Value)**, dan **Preferensi Harga (Avg Unit Price)** untuk menemukan pola belanja yang unik.

Alur proyek terdiri dari tiga tahapan utama:
1.  **Data Cleaning:** Membersihkan data transaksi mentah, membuang transaksi retur/negatif, dan menangani *outliers*.
2.  **Clustering (K-Means):** Mengelompokkan pelanggan menjadi 4 persona utama: *Big Spender, The Whales, Quality Seekers,* dan *Budget Shoppers*.
3.  **Business Simulation:** Menghitung potensi kenaikan pendapatan (*revenue uplift*) dengan menerapkan strategi promosi yang dipersonalisasi untuk setiap persona.

---

## 2. Informasi tentang Dataset
Proyek ini menggunakan dataset yang diambil dari **Kaggle**.

**Sumber Dataset**: https://www.kaggle.com/datasets/gabrielramos87/an-online-shop-business

### Konten Dataset

Dataset ini merupakan data transaksi penjualan dari sebuah e-commerce berbasis di Inggris (UK) selama periode satu tahun. Toko online yang berbasis di London ini telah menjual berbagai produk hadiah (gifts) dan perlengkapan rumah tangga (homewares) untuk orang dewasa maupun anak-anak melalui website sejak tahun 2007.

Pelanggan toko ini berasal dari berbagai negara di seluruh dunia dan umumnya melakukan pembelian langsung untuk kebutuhan pribadi. Selain itu, terdapat pula pelanggan bisnis skala kecil yang membeli produk dalam jumlah besar (bulk purchase) untuk dijual kembali kepada pelanggan lain melalui saluran ritel.

Dataset ini terdiri dari sekitar 500.000 baris data dan 8 kolom. Berikut adalah penjelasan masing-masing kolom:

- TransactionNo (kategorikal): Nomor unik enam digit yang merepresentasikan setiap transaksi.
Huruf “C” pada kode menandakan transaksi pembatalan (cancellation).

- Date (numerik): Tanggal ketika transaksi dilakukan.

- ProductNo (kategorikal): Kode unik lima atau enam digit yang digunakan untuk mengidentifikasi setiap produk.

- Product (kategorikal): Nama produk atau item yang dijual.

- Price (numerik): Harga satuan setiap produk dalam mata uang Pound Sterling (£).

- Quantity (numerik): Jumlah unit produk dalam setiap transaksi. Nilai negatif menandakan transaksi retur atau pembatalan.

- CustomerNo (kategorikal): Nomor unik lima digit yang mengidentifikasi setiap pelanggan.

- Country (kategorikal): Nama negara tempat tinggal pelanggan.

---

## 3. Petunjuk Setup Environment

Ikuti langkah-langkah berikut untuk menyiapkan lingkungan kerja lokal Anda agar kode dapat berjalan tanpa error.

### Prasyarat
- Python > 3.10.
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
