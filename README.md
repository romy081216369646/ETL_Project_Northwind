# Proyek ETL & Data Warehouse – Northwind Dataset

## Deskripsi Proyek
Proyek ini merupakan implementasi **ETL (Extract, Transform, Load)** dan **Data Warehouse** menggunakan **Northwind Dataset** sebagai data dummy.  
Tujuan proyek adalah membangun data warehouse dengan **skema bintang (Star Schema)** untuk mendukung analisis penjualan dan pengambilan keputusan bisnis.

Dataset Northwind dipilih karena memiliki struktur data yang lengkap, saling berelasi, serta umum digunakan untuk studi kasus pengolahan data penjualan.

---
Anggota kelompok:
-Romy Mahardika Pangestu Lazuardi (27)
---

## Sumber Data
Dataset yang digunakan adalah **Northwind Dataset (Dummy Data Publik)** yang diperoleh dari:
- Kaggle 
- Format data: CSV 

### Tabel Sumber Data
- `customers`
- `products`
- `orders`
- `order_details`
- `employees`
- `categories`
- `shippers`

---

## Tujuan Proyek
1. Mengimplementasikan proses ETL dari data dummy ke data warehouse
2. Merancang **Star Schema** yang optimal
3. Menghasilkan data terstruktur untuk analisis bisnis
4. Menganalisis **Key Performance Indicators (KPI)** penjualan
5. Menyajikan hasil analisis dalam bentuk visualisasi dashboard

---

## Arsitektur Data Warehouse

### Skema Bintang (Star Schema)

**Tabel Fakta:**
- `Fact_Penjualan`

**Tabel Dimensi:**
- `Dim_Pelanggan`
- `Dim_Produk`
- `Dim_Karyawan`
- `Dim_Pengirim`
- `Dim_Waktu`

Tabel fakta terhubung ke tabel dimensi menggunakan **foreign key** untuk mendukung analisis multidimensi.

---

## Proses ETL

### 1. Extract
- Mengambil data dari file CSV Northwind
- Data diekstrak menggunakan **Pentaho Data Integration (Kettle)**

### 2. Transform
- Pembersihan data (data cleaning)
- Normalisasi format tanggal
- Penghapusan data duplikat
- Join antar tabel (orders & order_details)
- Perhitungan total penjualan:
  total_penjualan = quantity × unit_price × (1 - discount)


### 3. Load
- Load data ke tabel dimensi terlebih dahulu
- Dilanjutkan dengan load ke tabel fakta
- Menjaga integritas data (primary key & foreign key)

---

## KPI (Key Performance Indicators)
Beberapa KPI yang dianalisis dalam proyek ini:
1. Total penjualan per periode (bulan/tahun)
2. Top 5 produk terlaris
3. Penjualan berdasarkan pelanggan
4. Kinerja karyawan berdasarkan penjualan

---

## Visualisasi Data
Hasil data warehouse divisualisasikan menggunakan tools Business Intelligence, seperti:
- Looker

Visualisasi yang ditampilkan:
- Diagram produk terlaris

---

## Struktur Repository
ETL_Project_Northwind
│── pentaho(.ktr)
│── sql
│── visualisasi
│── laporan Final.pdf 
│── README.md 


---

## Tools & Teknologi
- Pentaho Data Integration (ETL)
- MySQL (Data Warehouse)
- SQL
- Looker (Visualisasi)
- GitHub (Version Control)

---

## Kesimpulan
Proyek ini berhasil membangun data warehouse berbasis **Star Schema** dan mengimplementasikan proses ETL yang terstruktur. Data yang dihasilkan siap digunakan untuk analisis penjualan dan mendukung pengambilan keputusan bisnis berbasis data.

---

## Lisensi
Dataset Northwind digunakan hanya untuk **keperluan akademik dan pembelajaran**.

