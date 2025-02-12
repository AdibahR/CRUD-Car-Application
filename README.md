# Sistem Manajemen Rental Mobil

## Deskripsi Program

Program **Sistem Manajemen Rental Mobil** adalah aplikasi berbasis Python yang memungkinkan pengguna untuk menyewa mobil, mengembalikan mobil yang disewa, dan bagi admin untuk mengelola inventaris mobil melalui operasi CRUD (Create, Read, Update, Delete). Aplikasi ini menyediakan antarmuka menu interaktif yang mudah digunakan, baik untuk pelanggan maupun administrator, serta dilengkapi dengan fitur autentikasi untuk keamanan akses.

## Fitur Utama

- **Penyewaan Mobil:** Pelanggan dapat melihat daftar mobil yang tersedia, memilih mobil berdasarkan nomor plat, menentukan jumlah hari sewa, serta mendapatkan perhitungan biaya dan struk penyewaan.
- **Pengembalian Mobil:** Pelanggan dapat mengembalikan mobil yang telah disewa, dengan sistem yang memperbarui status ketersediaan dan menampilkan struk pengembalian.
- **Layanan Bantuan:** Fitur untuk menghubungi customer service dengan memasukkan nama dan pesan yang akan diteruskan untuk tindak lanjut.
- **Manajemen Inventaris (CRUD) oleh Admin:**
  - **Create:** Menambahkan mobil baru ke dalam sistem dengan validasi data.
  - **Read:** Menampilkan daftar seluruh mobil, mobil yang tersedia, dan mobil yang sedang disewa.
  - **Update:** Memperbarui informasi mobil (model, tarif harian, warna, rating, dan fitur unggulan).
  - **Delete:** Menghapus data mobil berdasarkan nomor plat.
- **Autentikasi:** 
  - **Pelanggan:** Registrasi dan login menggunakan username dan password.
  - **Admin:** Login dengan password khusus untuk mengakses fitur administrasi.

## Deskripsi Data

Data mobil disimpan dalam variabel `Aset_Mobil` dengan format sebagai berikut:

| No | Nama Kolom       | Tipe Data   | Deskripsi                                          |
|----|------------------|-------------|----------------------------------------------------|
| 1  | `Plat`           | `str`       | Nomor plat mobil yang unik                         |
| 2  | `Model`          | `str`       | Model mobil                                        |
| 3  | `Tarif Harian`   | `int`       | Tarif sewa mobil per hari (dalam Rupiah)           |
| 4  | `Warna`          | `str`       | Warna mobil                                        |
| 5  | `Rating`         | `float`     | Rating mobil (skala 0.0 - 5.0)                       |
| 6  | `Ketersediaan`   | `bool`      | Status ketersediaan mobil (`True`/`False`)         |
| 7  | `fitur_unggulan` | `list[str]` | Daftar fitur unggulan yang dimiliki mobil          |

## Menu Utama

Program ini menawarkan dua jenis pengguna dengan menu utama yang berbeda:

### 1. Menu Pelanggan

Setelah proses login atau registrasi, pelanggan dapat mengakses fitur-fitur berikut:

- **Yuk Sewa Mobil**
  - **Sewa Mobil:** Menampilkan daftar mobil yang tersedia, memilih mobil berdasarkan plat, memasukkan jumlah hari sewa, dan mendapatkan perhitungan total biaya. Konfirmasi penyewaan akan mengubah status ketersediaan dan menyimpan data transaksi.
  - **Cek Fitur dan Rating Mobil:** Menampilkan informasi lengkap mengenai fitur unggulan dan rating setiap mobil yang ada.
  
- **Balikin Mobil Yuk**
  - Menampilkan daftar mobil yang sedang disewa, memungkinkan pelanggan untuk mengembalikan mobil dengan memilih berdasarkan plat dan mendapatkan struk pengembalian.
  
- **Layanan Bantuan Pelanggan**
  - Pelanggan dapat mengirimkan pesan atau pertanyaan kepada customer service dengan memasukkan nama dan pesan.

### 2. Menu Admin

Admin dapat mengelola data mobil melalui menu yang berisi:

- **Tambah Mobil Baru (Create):**
  - Menambahkan mobil baru dengan input data seperti plat (unik), model, tarif harian, warna, rating, dan fitur unggulan.
  
- **Lihat Daftar Mobil (Read):**
  - Menampilkan seluruh data mobil, termasuk daftar mobil yang tersedia dan mobil yang sedang disewa. Juga menyediakan opsi pencarian berdasarkan kategori seperti plat, model, warna, dan rating.
  
- **Update Informasi Mobil (Update):**
  - Memperbarui data mobil yang sudah ada berdasarkan nomor plat, dengan opsi untuk mengubah model, tarif, warna, rating, dan fitur unggulan.
  
- **Hapus Data Mobil (Delete):**
  - Menghapus data mobil dari sistem setelah konfirmasi dari admin.

- **Keluar:**
  - Mengembalikan admin ke menu utama.

## Autentikasi

### Pelanggan
- **Registrasi:** Pengguna baru dapat mendaftar dengan memasukkan username dan password yang unik.
- **Login:** Pengguna yang telah terdaftar dapat masuk dengan menggunakan kredensial yang telah dibuat.

### Admin
- **Login Admin:** Admin mengakses sistem dengan memasukkan password khusus (`admin123`) untuk mengakses menu administrasi.

## Alur Program

1. **Menu Awal:**
   - Pengguna memilih untuk login sebagai **Pelanggan** atau **Admin**.
   
2. **Autentikasi:**
   - **Pelanggan:** Bisa memilih untuk registrasi (sign up) atau langsung login.
   - **Admin:** Langsung melakukan login dengan memasukkan password admin.
   
3. **Akses Menu Sesuai Peran:**
   - Pelanggan akan mengakses menu penyewaan dan layanan bantuan.
   - Admin akan mengakses menu untuk mengelola data mobil (CRUD).
   
4. **Eksekusi Transaksi:**
   - Pelanggan melakukan penyewaan atau pengembalian mobil.
   - Admin melakukan operasi tambah, lihat, update, atau hapus data mobil.
   
5. **Logout/Keluar:**
   - Pengguna dapat keluar dari sesi dan kembali ke menu awal.

## Cara Menjalankan Program

1. **Prasyarat:**
   - Pastikan Python 3.x sudah terinstal pada sistem Anda.
   - Instal modul yang diperlukan menggunakan pip:
     ```bash
     pip install colorama tabulate
     ```
2. **Menjalankan Aplikasi:**
   - Buka terminal/command prompt.
   - Arahkan ke direktori tempat file program disimpan.
   - Jalankan program menggunakan perintah:
     ```bash
     python nama_file.py
     ```
3. **Interaksi:**
   - Ikuti petunjuk pada layar untuk melakukan registrasi, login, dan memilih menu yang diinginkan.

## Limitasi Program

Meskipun program ini telah menyediakan berbagai fitur untuk manajemen rental mobil, terdapat beberapa keterbatasan, antara lain:

- **Penyimpanan Data Sementara:**  
  Data mobil dan transaksi penyewaan hanya disimpan dalam memori selama program berjalan. Tidak ada integrasi dengan basis data atau file penyimpanan, sehingga data akan hilang saat program ditutup.

- **Keamanan Input:**  
  Meskipun terdapat validasi input, program ini belum memiliki mekanisme keamanan tingkat lanjut seperti enkripsi password atau perlindungan terhadap serangan injeksi.

- **Skalabilitas:**  
  Program ini dirancang untuk penggunaan skala kecil. Pada penggunaan dengan jumlah pengguna atau transaksi yang sangat banyak, performa dapat menurun karena tidak ada manajemen concurrency atau sistem caching.

- **Antarmuka Pengguna:**  
  Antarmuka berbasis teks di terminal memiliki keterbatasan dalam hal interaktivitas dan keindahan tampilan dibandingkan dengan aplikasi berbasis GUI atau web.

- **Fitur Transaksional:**  
  Program belum mendukung fitur pembayaran online atau integrasi dengan sistem gateway pembayaran. Semua transaksi hanya berupa perhitungan sederhana dan pencetakan struk di layar.

- **Penanganan Error:**  
  Meskipun ada validasi untuk input, program belum mengimplementasikan sistem logging atau penanganan error yang komprehensif untuk situasi di luar skenario yang sudah diantisipasi.

## Kesimpulan

Program **Sistem Manajemen Rental Mobil** merupakan solusi sederhana untuk kebutuhan rental mobil berbasis terminal yang mendemonstrasikan konsep dasar pemrograman, pengelolaan data, dan operasi CRUD. Dengan pengembangan lebih lanjut, fitur-fitur seperti penyimpanan data permanen, antarmuka pengguna yang lebih menarik, dan integrasi sistem pembayaran dapat ditambahkan untuk meningkatkan fungsionalitas dan skalabilitas aplikasi.

---
*Catatan: Program ini merupakan proyek sederhana untuk pembelajaran dan demonstrasi konsep pemrograman Python. Pengembangan lebih lanjut diperlukan untuk penggunaan di lingkungan produksi.*
