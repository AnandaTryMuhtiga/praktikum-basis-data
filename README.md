📘 Ringkasan Modul Praktikum Basis Data — Bab 1 & Bab 2
BAB 1 — Review Konversi ER Diagram ke Skema Relasi
🎯 Kompetensi

Memahami cara mengonversi ER Diagram → Skema Relasi → Tabel fisik.

Memudahkan proses transformasi desain database menjadi implementasi nyata.

📌 Topik Utama

Konversi ER ke Skema Relasi & Diagram Relationship

Studi kasus: Skema Order Entry

🧩 Konversi ER ke Skema Relasi — Aturan Inti

Beberapa aturan dasar dalam konversi ERD:

✔ 1. Strong Entity → Tabel

Nama entitas = nama tabel

Simple attribute = kolom

Primary key tetap

✔ 2. Composite Attribute

Dipecah menjadi beberapa kolom

✔ 3. Multivalue Attribute

Dibuat tabel baru

Primary key entitas induk → foreign key

✔ 4. Weak Entity

Menjadi tabel

Primary key = kombinasi (PK entitas kuat + atribut identifikasi)

✔ 5. Relationship

1 : 1 → FK pada salah satu tabel

1 : N → FK di tabel sisi “many”

N : M → Membuat tabel relasi baru

Unary & Ternary Relationship → Aturan khusus (self join / tabel relasi)

🏥 Studi Kasus: Skema Pembayaran Apotik

Modul menyediakan ERD lengkap mencakup:

Pasien, Pegawai, Obat, Pembayaran, Resep, Kategori, Retur, dan lainnya

Total tabel hasil konversi: 13 tabel

BAB 2 — Pengantar Basis Data & DDL
🎯 Kompetensi

Memahami dasar-dasar database dan DBMS.

Mengenal aplikasi MySQL (server & client).

Mengetahui tipe data MySQL.

Menggunakan perintah dasar Data Definition Language (DDL).

📌 Topik Utama

MySQL & instalasi

MySQL Server & Client

Mengakses MySQL via CMD

Tipe Data MySQL

Dasar-dasar Database Relasional

Perintah DDL: CREATE, SHOW, USE, DROP

🗄️ DBMS MySQL

DBMS open-source, cepat, reliable, dan mendukung multi-platform.

Menggunakan bahasa SQL.

Sering digunakan dalam pengembangan aplikasi web.

🖥️ Aplikasi Pendukung

XAMPP → sudah termasuk MariaDB/MySQL

MySQL Server dijalankan sebagai service

MySQL Client (mysql.exe) digunakan untuk mengetik perintah SQL

🔑 Cara Mengakses MySQL

CMD:

cd C:\xampp\mysql\bin
mysql -u root -p

🔤 Tipe Data MySQL
Tipe Data	Keterangan
INT	Bilangan bulat
FLOAT	Bilangan desimal
DATE	YYYY-MM-DD
DATETIME	Tanggal & waktu
CHAR	String fix
VARCHAR	String fleksibel
BLOB	Data besar
🧱 DDL (Data Definition Language)
1. Membuat Database
CREATE DATABASE nama_db;

2. Melihat Semua Database
SHOW DATABASES;

3. Menggunakan Database
USE nama_db;

4. Menghapus Database
DROP DATABASE nama_db;
