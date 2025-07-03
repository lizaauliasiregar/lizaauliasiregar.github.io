---
layout: post 
title: "Mengumpulkan Tugas Menggunakan Github Classroom"
---

Disini akan dijelaskan langkah-langkah untuk mengapload tugas program menggunakan Github Classroom

<h4>Langkah-Langkah</h4>

1. Login ke akun Github masing-masing.
2. Jika sudah login, kemudian klik tautan classroom yang dibagikan dosen
3.  Masuk ke tautan tersebut. Jika dimintai untuk login, maka login. Setelah itu klik "Authorize"
4. Kemudian akan muncul halaman baru, klik "Accept this assignment"
5. Jika tulisan "You’re ready to go!" maka sudah berhasil, dan repository baru sudah tersedia.
6. Pada repository baru tersebut, pilih bagian "Code" lalu salin bagian SSH yang tersedia
7. Lalu masuk ke folder local di pc masing-masing dan buka gitbush dari folder tersebut dan ketik:
    
    git clone git@github.com:JTIK-PNL/php-crud-lizaauliasiregar.git
Lalu Enter. Tunggu sampai selesai. Jika sudah selesai, akan terbentuk sebuah folder
8. Masuk dalam folder tersebut lalu paste semua file yang sudah dibuat selama praktikum-praktikum sebelumnya. Jika sudah, ketik :
    
    git add .

    git commit -m "initial commit"
    
    git push

9. Selesai. Semua folder berhasil di push kedalam repository baru tersebut 