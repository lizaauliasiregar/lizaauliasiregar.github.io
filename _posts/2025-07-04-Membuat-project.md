---
layout: post 
title: "Instalasi Laratih/Laravel"
---
Instalasi Laratih/Laravel

<h1>Langkah Kerja</h1>

1. buat project => composer create-project --prefer-dist laravel/laravel laratih
2. install breeze => composer require laravel/breeze --dev
3. jalankan perintah untuk menginstall Breeze => php artisan breeze:install
4. jalankan perintah untuk menginstall npm => npm install
5. jalankan perintah untuk mengcompile asset => npm run dev
6. buat model dan migration untuk table Siswa => php artisan make:model Siswa
7. buat file controller untuk Siswa => php artisan make:controller SiswaController --model=Siswa
8. isi file migration yang ada di direktori database/migration dengan kode berikut:
    $table->id();
    $table->string('nama', 100);
    $table->text('alamat');
    $table->string('agama');
    $table->boolean('jenis_kelamin'); // 1 untuk laki-laki, 0 untuk perempuan
    $table->string('asal_sekolah');
    $table->timestamps();
9. pastikan koneksi ke database sudah benar di file .env
   - ubah DB_CONNECTION, DB_HOST, DB_PORT, DB_DATABASE, DB_USERNAME, dan DB_PASSWORD sesuai dengan konfigurasi database Anda.
   - contoh:
     ```
     DB_CONNECTION=mysql
     DB_HOST=localhost
     DB_PORT=3306
     DB_DATABASE=dev_mahasiswa
     DB_USERNAME=root
     DB_PASSWORD=

10. jalankan perintah untuk migrasi database => php artisan migrate
11. jalankan perintah untuk membuat user melalui seeder => php artisan db:seed