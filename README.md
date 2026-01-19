<p align="center"> <img src="https://lh3.googleusercontent.com/d/1-TrhdCX8Geg0MPz6wW44Gst2bRhawRC3" width="300" alt="TRPL Logo"> </p>
<h1 align="center">🛒 Sistem Transaksi Penjualan Toko Maju Homeware 🛒</h1>
<p align="center"> <b>Management System Transaksi</b>
  
# Project-Akhir-Sistem-Basis-Data
👥 Anggota Kelompok 👥
1. Muhammad Nur Hasan Majid [250119017]
2. Adnan Muhammad Fihr      [250119002]
3. Aditya Firmansyah        [250119001]

**🛠️ Sistem Basis Data Inventori & Transaksi (UAS)**

__Proyek Akhir Mata Kuliah Sistem Basis Data - Universitas Duta Bangsa Surakarta__

📝 1. Deskripsi Proyek 📝

Proyek ini adalah sistem manajemen basis data relasional yang dirancang untuk toko retail alat rumah tangga (Studi Kasus: Toko Wadah Plastik). Sistem ini mengintegrasikan pendataan barang, manajemen pemasok (vendor), serta pencatatan transaksi penjualan yang melibatkan kasir, sales, dan pelanggan.

🛠️ 2. Tools yang Digunakan 🛠️

a. MySQL: Sebagai Sistem Manajemen Database (DBMS).
b XAMPP: Sebagai server lokal untuk menjalankan layanan MySQL (MariaDB).
c. MySQL Workbench / phpMyAdmin: (Opsional) Untuk mempermudah eksekusi query dan visualisasi data.

📂 3. Struktur Repository 📂

  A. DATABASE dan QUERY.sql : Berkas utama berisi seluruh perintah DDL, DML, dan kueri analisis.
  
  B. Laporan_SBD_Kelompok04.pdf : Laporan resmi lengkap (Bab 1 - Bab 4).
  
  C. Poster_SBD_Kelompok04.pdf : Poster publikasi proyek.

📂--- 4. Struktur Database ---📂

Proyek ini terdiri dari beberapa tabel utama:
1. barang: Menyimpan detail item, stok, dan harga.
2. jenisBarang: Kategorisasi barang (Alat Makan, Tempat Minum, Toples).
3. kasir: Data petugas kasir.
4. sales: Data petugas sales.
5. pelanggan: Data pelanggan.
6. vendor: Hubungan antara pemasok dan barang yang disediakan.
7. transaksi & detailBarang: Mencatat histori penjualan dan rincian item.

📊 5. Langkah Instalasi & Setup Database 📊

1. install dan buka xampp jalankan (start) Apache dan MySQL
2. install dan buka MySQL setelah itu setup new connetion dan buat data base

🧬 6. Rancangan Database (Sub-Bab Detail) 🧬

🏗️ A. Data Definition Language (DDL)

Kami membangun database bernama UAS dengan 7 tabel utama. Setiap tabel menggunakan mesin penyimpanan InnoDB untuk mendukung Foreign Key dan ACID Transactions.

          Tabel Master:

 a. jenisBarang: Kategori produk (Alat Makan, Minum, Toples).

 b. barang: Detail item (Stok, Harga, Unit).

 c. vendor: Data pemasok beserta lokasi (Jakarta, Bandung, Surabaya).

 d. kasir & sales: Entitas internal yang melayani transaksi.

 e. pelanggan: Data identitas pembeli.

        Tabel Transaksi:

 a. transaksi: Header transaksi (Nomor nota, Tanggal, Total, Kembalian).

 b. detailBarang: Tabel penghubung antara transaksi dan item barang yang dibeli.

📥 B. Data Manipulation Language (DML)

Kami telah memasukkan data simulasi (seed data) yang mencakup:

 a. 10 variasi produk (Tupperware, Piring, Sendok, dll).

 b. 3 Vendor utama dengan sebaran lokasi berbeda.

 c. Skenario transaksi lengkap dengan perhitungan kas dan kembalian.

🔍 7. Analisis Query (Fitur Utama) 🔍

📊 Agregasi & Grouping 

Sistem mampu mengelompokkan barang berdasarkan kategorinya dan menghitung total stok secara otomatis menggunakan GROUP BY dan SUM.

🔗 Multi-Table Join
Implementasi kueri kompleks untuk menghasilkan laporan yang transparan:

Inner Join: Menampilkan nama Kasir dan Sales pada struk penjualan.

Left Join: Audit barang untuk melihat barang mana yang belum memiliki vendor.

Full Join (Union): Rekonsiliasi total antara data barang dan data vendor.

🛡️ Transaction Control (TCL)

Sistem menjamin konsistensi data. Jika terjadi kegagalan sistem saat pengurangan stok (UPDATE), perintah ROLLBACK akan mengembalikan kondisi stok ke awal sehingga tidak ada data yang hilang atau salah.


💻 8. Cara Menjalankan Program 💻
1. (Dasar): Cukup `SELECT` untuk memunculkan atau melihat isi didalam tabel
2. (Pencarian): Menggunakan `LIKE` untuk mencari barang di tabel
3. (Filter): Menggunakan `BETWEEN` untuk Menampilkan barang yang memiliki stok kritis antara 2 sampai 10 unit
4. 4 & 5 (Join): Kami pilih `Inner Join` (paling sering dipakai) dan `Left Join` (untuk melihat barang yang mungkin belum punya vendor).

📚 9. Referensi 📚

Irawan RD. Modul Praktikum Pemrograman Basis Data. UDB Surakarta; 2024.

Silberschatz A. Database System Concepts. 7th ed. McGraw-Hill; 2019.
