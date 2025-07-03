---
layout: post
title: "HTML Link dan Lists"
---

Penjelasan tentang link dan list pada HTML.

![HTML_Link_dan_Listet](/assets/images/WALPA.jpg)

<h1>HTML : Link dan List</h1>
<h2>HTML: Link (Tautan)</h2>
Link digunakan untuk menghubungkan satu halaman dengan halaman lainnya, file, atau website lain. 

<h4>Sturktur Dasar Link</h4>

    <a href="https://www.contoh.com">Klik di sini</a>
    - href = atribut utama, menunjukkan alamat tujuan link.
    - Teks di antara <a> dan </a> adalah teks yang bisa diklik.

<h4>Contoh Link</h4>

    <a href="halaman2.html">Lanjut ke Halaman 2</a>
    <a href="https://google.com" target="_blank">Cari di Google</a>

- target="_blank" akan membuka link di tab baru.

<h4>HTML: List (Daftar)</h4>
Ada dua jenis daftar Utama. Diantaranya

**1. Ordered List (dafatr berurutan)**
    
    Menggunakan tag <ol> dan <li>. Contoh :
        <ol>
        <li>Kucing</li>
        <li>Liza</li>
        <li>Makan</li>
        </ol>


**2. Unordered List (daftar tidak berurutan)**
    
    Menggunakan tag <ul> dan <li>. Contoh :
        <ul>
        <li>Kopi</li>
        <li>Teh</li>
        <li>Susu</li>
        </ul>

**3. Link di dalam List**
    
    Bisa menambahkan tautan (link) ke dalam setiap item list dengan cara meletakkan elemen <a> di dalam <li>.
Contoh :
    
    <ul>
    <li><a href="https://www.google.com">Google</a></li>
    <li><a href="https://www.youtube.com">YouTube</a></li>
    <li><a href="https://www.wikipedia.org">Wikipedia</a></li>
    </ul>


<h3>Kesimpulan</h3>
    
    - List (<ul> atau <ol>) digunakan untuk menampilkan data dalam bentuk poin atau nomor
    - Link (<a>) dimasukkan ke dalam elemen list (<li>) menjadi tautan
     