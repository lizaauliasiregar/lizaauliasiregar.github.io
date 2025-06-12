---
layout: post 
title: "Membuat Personal Web dengan Jekyll dan GitHub Page"
---
Membuat Personal Web dengan Jekyll dan GitHub Page

    1. Buat repository baru dengan nama username dan github.io.
      Contoh: username github = zaauliasiregar, maka nama repositorinya zaauliasiregar.github.io
    2. Clone repository tersebut ke local.
    3. Kemudian masuk ke dalam folder repository tersebut dan install melalui terminal Visual studio code dengan perintah dibawah ini:
        * gem install jekyll bundler
        * bundle init
    4. Masuk ke folder Gemfile yang muncul dan tambahkan 
        * gem “jekyll” di baris baru
    5. Tambahkan file baru dengan nama index.html dan isi dengan kode berikut 
        <!DOCTYPE html>
        <html>
        <head>
        <meta charset="utf-8">
        <title>Home</title>
        </head>
        <body>
        <h1>Hello World!</h1>
        </body>
        </html>
    6. Kemudian jalankan jekyll build di terminal untuk build web yang telah dibuat agar menhasilkan directory _site.
    7. Jalankan juga “jekyll serve” dan klik url  http://127.0.0.1:4000 yang muncul.
    8. Jika web sudah berhasil dibuka, edit Gemfile.lock dan tambahkan “x86_64-linux” pada bagian “Platforms”
    9. Push repositori ke GitHub dengan perintah-perintah:
        * git add .
        * git commit -m “pub: first publish”
        * git push
