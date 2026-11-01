# HealthyMate

HealthyMate adalah aplikasi web berbasis Flask yang dirancang sebagai asisten kesehatan dan nutrisi pintar. Aplikasi ini membantu pengguna memantau asupan kalori harian, berkonsultasi dengan dokter spesialis gizi, dan mengelola jadwal kesehatan secara terpusat. 

Aplikasi ini memiliki 3 peran pengguna utama: **Pasien**, **Dokter**, dan **Admin**, yang masing-masing memiliki fitur dan alur kerja tersendiri.

---

## Panduan Penggunaan Aplikasi (Alur Pasien)

### 1. Halaman Utama (Welcome Page)
Saat pertama kali membuka aplikasi, pengguna akan disambut dengan halaman beranda yang menampilkan ringkasan layanan, kutipan motivasi kesehatan, dan tombol untuk memulai.
> **Gambar Halaman Utama:**
> `![Welcome Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm01.avif)`

### 2. Registrasi Akun
Jika belum memiliki akun, pengguna dapat mendaftar melalui halaman **Sign Up** dengan mengisi Username, Email, dan Password.
> **Gambar Halaman Registrasi:**
> `![Register Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm02.avif)`

### 3. Login ke Aplikasi
Setelah mendaftar, pengguna masuk melalui halaman **Log In**. Setelah berhasil login, pengguna akan diarahkan ke halaman Dashboard. Pada tahap awal, dashboard mungkin akan terlihat kosong karena data profil belum dilengkapi.
> **Gambar Halaman Login:**
> `![Login Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm03.avif)`

### 4. Melengkapi Profil & Data Kesehatan
Pengguna wajib melengkapi data profil seperti **Umur, Berat Badan, Tinggi Badan, Gender, dan Tingkat Aktivitas**. Data ini akan digunakan sistem untuk menampilkan ringkasan di halaman Dashboard dan menghitung estimasi kebutuhan kalori harian (BMR & TDEE).
> **Gambar Halaman Profil:**
> `![Profile Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm04.avif)`

Setelah profil terisi, halaman **Dashboard** akan menampilkan data *personal health* dan kalkulasi *Daily Calorie Needs* secara otomatis berdasarkan data profil.
> **Gambar Halaman Dashboard:**
> `![Dashboard Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm05.avif)`

### 5. Menggunakan Kalkulator Nutrisi
Pengguna dapat menggunakan fitur **Calculator** untuk menghitung kebutuhan kalori berdasarkan skenario baru. Di sini pengguna dapat mengubah intensitas latihan dan tujuan (*Weight Gain* atau *Weight Loss*) untuk melihat rekomendasi kalori dan pembagian porsi makan (Breakfast, Lunch, Dinner). *Catatan: Perhitungan di kalkulator ini tidak akan mengubah data profil utama pengguna.*
> **Gambar Halaman Kalkulator:**
> `![Calculator Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm06.avif)`

### 6. Riwayat Kalkulasi
Setiap hasil perhitungan dari fitur Kalkulator akan disimpan secara otomatis. Pengguna dapat melihat, mengelola, dan menghapus riwayat kalkulasi mereka melalui halaman **Calculation History**.
> **Gambar Halaman Riwayat Kalkulasi:**
> `![History Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm07.avif)`

### 7. Halaman Konsultasi
Melalui menu **Consultation**, pengguna dapat melihat daftar dokter spesialis gizi yang tersedia. Di sini tertera informasi status (Available/Vacation), jadwal praktik, dan tombol untuk membuat janji temu.
> **Gambar Halaman Konsultasi:**
> `![Consultation Page](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm10.avif)`

### 8. Membuat Janji Temu (Appointment)
Pengguna dapat membuat janji temu dengan memilih jadwal yang tersedia (hari dan jam kosong), memasukkan nomor WhatsApp aktif, serta menuliskan keluhan atau topik konsultasi.
> **Gambar Form Janji Temu:**
> `![Make Appointment Form](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm08.avif)`

### 9. Menunggu Konfirmasi Admin
Setelah janji temu diajukan, status janji temu akan menjadi *Pending*. Pengguna harus menunggu persetujuan dari Admin melalui panel admin. Jika pengguna mencoba membuat janji temu baru saat masih ada janji berstatus *Pending*, sistem akan menolak dan meminta pengguna menunggu.
> **Gambar Status Pending:**
> `![Pending Appointment](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm09.avif)`

---

## Fitur Panel Admin

Admin bertugas mengelola operasional aplikasi, pengguna, dan persetujuan jadwal.

### 1. Overview Dashboard
Halaman utama admin menampilkan ringkasan jumlah pasien, dokter, total janji temu, dan daftar permintaan janji temu terbaru (*Needs Approval*) yang harus segera diproses (Approve/Reject).
> **Gambar Dashboard Admin:**
> `![Admin Dashboard](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm11.avif)`

### 2. Manajemen Appointment
Admin dapat melihat seluruh riwayat dan data janji temu dari semua pasien, lengkap dengan statusnya (*Pending, Approved, Rejected, Expired, Completed*). Admin dapat menyetujui atau menolak pengajuan secara langsung.
> **Gambar Manajemen Appointment:**
> `![Admin Appointments](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm12.avif)`

### 3. Manage Users
Admin dapat mengelola seluruh pengguna terdaftar (Pasien, Dokter, Admin). Admin juga memiliki akses eksklusif untuk menambah akun Dokter baru melalui tombol **Add Doctor**.
> **Gambar Manage Users:**
> `![Admin Manage Users](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm13.avif)`

### 4. Persetujuan Jadwal (Schedule Approvals)
Jika dokter mengajukan perubahan jadwal praktik, admin akan menerima proposal di halaman ini. Jika disetujui (*APPROVED*), jadwal baru dokter tersebut akan otomatis berlaku pada minggu berikutnya.
> **Gambar Schedule Approvals:**
> `![Admin Schedule Approvals](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm14.avif)`

### 5. Notification Center (Broadcast)
Admin dapat mengirimkan notifikasi manual (pengumuman) kepada seluruh pengguna aplikasi (Pasien & Dokter) atau menargetkan pengguna tertentu.
> **Gambar Notification Center:**
> `![Admin Notifications](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm15.avif)`

---

## Fitur Panel Dokter

Dokter memiliki dasbor khusus untuk mengelola agenda praktik dan konsultasinya dengan pasien.

### 1. Dashboard Dokter
Halaman ini menampilkan ringkasan *Upcoming Appointments* (jadwal pasien yang harus dilayani) dan *Consultation History (Completed)* (riwayat pasien yang sudah selesai dikonsultasikan). Dokter juga dapat melihat jadwal praktik aktifnya.
> **Gambar Dashboard Dokter:**
> `![Doctor Dashboard](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm16.avif)`

### 2. Detail Riwayat Konsultasi (Consultation Summary)
Saat dokter mengklik detail dari riwayat konsultasi, akan muncul halaman *Consultation Summary*. Halaman ini berisi informasi lengkap:
- Nama Pasien & Dokter
- Waktu dan Durasi Konsultasi
- Keluhan Awal (Initial Patient Complaint)
- Catatan & Rekomendasi Dokter (Doctor's Notes)
- Tombol untuk melihat *History Chat* konsultasi.
> **Gambar Consultation Summary:**
> `![Consultation Summary](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm17.avif)`

### 3. Pengajuan Perubahan Jadwal (Practice Schedule Proposal)
Dokter dapat mengajukan perubahan jadwal (hari dan jam) praktiknya melalui menu **Submit Practice Schedule Change**. Dokter dapat menambah atau menghapus blok waktu pada hari tertentu. Proposal ini harus disetujui oleh Admin sebelum berlaku.
> **Gambar Form Proposal Jadwal:**
> `![Doctor Schedule Proposal](https://hdaphuncqwjfxysgmcew.supabase.co/storage/v1/object/public/images/hm18.avif)`

---

## Struktur Project & Instalasi

Untuk informasi lebih lanjut mengenai cara mengunduh project, mengatur *Virtual Environment*, konfigurasi database MySQL, migrasi, dan cara menjalankannya di komputer lokal, silakan baca panduan lengkapnya di file:

**[INSTALLATION.md](installation.md)**

## Kontribusi
Jika Anda ingin berkontribusi pada project ini, silakan lakukan *fork* pada repository ini, buat *branch* baru untuk fitur Anda, dan ajukan *Pull Request*.

---
*Copyright © 2026 HealthyMate. All rights reserved.*