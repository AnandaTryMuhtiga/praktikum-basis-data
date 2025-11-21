📘 Ringkasan Lengkap Modul Praktikum Basis Data (Bab 1–2)
## BAB 1 – Review Konversi ER Diagram ke Skema Relasi
🎯 Tujuan Pembelajaran

Bab ini bertujuan agar praktikan:

Memahami cara mengonversi ER Diagram → Skema Relasi → Tabel fisik.

Dapat melakukan transformasi dari level konseptual (ERD) ke level fisik (tabel database).

Siap membangun database MySQL berdasarkan desain ERD.

### 1. Dasar-dasar Konversi ER Diagram

Berikut aturan lengkap saat mengubah ER Diagram menjadi tabel:

1️⃣ Strong Entity → Tabel

Nama entitas menjadi nama tabel.

Atribut sederhana menjadi kolom.

Primary key tetap.

Contoh:
Entitas: Karyawan(nip, nama, alamat, tgl_lahir)
Tabel: Karyawan(nip PK, nama, alamat, tgl_lahir)

2️⃣ Composite Attribute

Atribut majemuk dipecah menjadi beberapa kolom.

Atribut induknya tidak menjadi kolom.

Contoh: alamat → jalan, kota, provinsi, kode_pos.

3️⃣ Multivalue Attribute

Menjadi tabel baru.

FK dari entitas induk digunakan.

Contoh:

Karyawan memiliki banyak hobi → tabel Hobby_Karyawan(nip FK, hobby)

4️⃣ Derived Attribute

Dapat dibuat menjadi kolom biasa jika perlu.

Contoh: umur dapat disimpan sebagai kolom.

5️⃣ Weak Entity

Menjadi tabel baru.

PK terdiri dari PK strong entity + partial key.

Contoh: Tanggungan(nip FK, nama_tgg, hubungan)

6️⃣ Relationship 1-to-1

Tambahkan FK pada salah satu tabel.

Dua alternatif:

FK di entitas A

FK di entitas B

Bergantung pada total participation.

7️⃣ Relationship 1-to-N

FK diletakkan pada entitas sisi N.

Contoh:
Karyawan (1) — mencatat — (N) Peminjaman
FK: Peminjaman.nip → Karyawan.nip

8️⃣ Relationship M-to-N

Dibuat tabel relasi baru.

Berisi:

FK entitas A

FK entitas B

Atribut relasi (jika ada)

Kadang menggunakan surrogate PK

9️⃣ Unary Relationship

1-to-1 → FK mengacu ke tabel yang sama

M-to-N → tabel relasi baru

🔟 Ternary Relationship

3 entitas → 4 tabel total

Tabel relasi berisi 3 FK + atribut relasi

1️⃣1️⃣ Generalisasi / Spesialisasi (ISA)

Dua metode:

Metode 1:

Ada tabel superclass

Ada tabel subclass

Subclass memiliki PK = PK superclass

Metode 2:

Hanya tabel subclass

Semua atribut superclass diturunkan ke subclass

1️⃣2️⃣ Agregasi

Relasi kompleks yang butuh tabel ekstra

Kombinasi M-to-N dan relasi lainnya

### Studi Kasus Besar: Skema Pembayaran Apotik

ERD terdiri dari entitas:

Pasien, Pasien_BPJS, Pasien_NonBPJS

Resep

Obat, Kategori_Obat

Detail_Obat

Pembayaran

Pegawai

Retur, Detail_Retur

Total tabel hasil konversi: 13 tabel

Contoh tabel:

PASIEN(#NoPasien, nama, alamat, pekerjaan, No_KTP)

OBAT(#KodeObat, Id_kategori, harga, dosis, jumlah)

RESEP(#NoResep, NoPasien, total, AsalDokter)

DETAIL_OBAT(#Id_det_ob, NoResep, KodeObat, Jumlah, Subtotal)

Semua foreign key ditandai dengan FK.

### Test Akhir Bab 1

Mengonversi ERD “Musisi – Promotor – Album – Gedung” menjadi tabel relasi.

Menghitung jumlah tabel.

## BAB 2 – Pengantar Basis Data & DDL
🎯 Tujuan Pembelajaran

Memahami konsep dasar database & DBMS.

Mengenal MySQL, instalasi, akses, command line, dan client.

Menggunakan perintah dasar DDL (Data Definition Language):

CREATE

SHOW

USE

DROP

### 2. Apa itu Database & DBMS?
📌 Database

Kumpulan data yang terorganisir.

Disimpan secara sistematis agar mudah diakses.

📌 DBMS (Database Management System)

Software untuk mengelola database.

Contoh:

MySQL

MariaDB

PostgreSQL

Oracle

SQL Server

### 3. MySQL

MySQL adalah DBMS open source yang:

Cepat, stabil, dan sangat populer.

Mendukung multi-platform.

Menggunakan bahasa SQL.

Mendukung multi-user & multithread.

Sangat cocok untuk aplikasi web.

### 4. Instalasi MySQL

Direkomendasikan menggunakan XAMPP

XAMPP versi terbaru menggunakan MariaDB

Perintah SQL tetap sama seperti MySQL

### 5. MySQL Server & Client
MySQL Server

Menyimpan database

Dijalankan melalui XAMPP Control Panel

MySQL Client

Program untuk mengetik perintah SQL

File: mysql.exe berada di xampp/mysql/bin

### 6. Mengakses MySQL via CMD

CMD:

cd C:\xampp\mysql\bin
mysql -u root -p


Password default: kosong

Keluar dari MySQL:

\q

### 7. Tipe Data MySQL
Tipe Data	Keterangan	Format/Ukuran
INT	Bilangan bulat	-2147483648 s/d +2147483647
FLOAT	Angka desimal	
DATE	Tanggal	YYYY-MM-DD
DATETIME	Tanggal & waktu	YYYY-MM-DD HH:MM:SS
CHAR(n)	String panjang tetap	1-255
VARCHAR(n)	String fleksibel	1-255
BLOB	Data besar	≤ 65.535 byte
LONGBLOB	Data lebih besar	≤ 4GB
### 8. Database Relasional

Database = kumpulan tabel
Tabel = kumpulan kolom (field) dan baris (record)

Untuk membuat tabel → harus berada di dalam database terlebih dahulu.

### 9. Perintah DDL (Data Definition Language)
1️⃣ CREATE DATABASE
CREATE DATABASE nama_db;

2️⃣ SHOW DATABASES
SHOW DATABASES;

3️⃣ USE DATABASE
USE nama_db;

4️⃣ DROP DATABASE
DROP DATABASE nama_db;
