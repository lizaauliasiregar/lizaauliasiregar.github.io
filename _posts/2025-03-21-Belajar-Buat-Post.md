---
layout: post 
title: "Belajar Buat Post"
---

Belajar Buat Post

Mempelajari cara membuat post dengan bahasa markdown

<h1>Cara Membuat Post dengan Markdown</h1>
Markdown adalah bahasa markup ringan yang dapat digunakan untuk menambahkan elemen pemformatan (seperti judul, daftar, tautan) ke teks biasa

<h3>Elemen Utama Struktur Markdown</h3>

<h4>1. Judul</h4>
Pakai tanda pagar "#" untuk membuat heading. Semakin banyak tanda pagar di depan teks, semakin kecil ukuran heading-nya (dari h1 hingga h6). 

    # Judul H1
    ## Judul H2
    ### Judul H3
    #### Judul H4
    ##### Judul H5
    ###### Judul H6

<h4>Paragraf</h4>
Untuk membuat paragraf, langsung ditulis saja. Markdown akan otomatis membaca baris kosong sebagai paragraf baru.

Ini adalah paragraf pertama.

Ini adalah paragraf kedua.

<h4>3. Menebalkan dan Memiringkan Teks</h4>
Untuk membuat teks tebal di Markdown, bungkus teks dengan dua tanda bintang atau garis bawah di setiap sisi. Untuk membuat teks miring, bungkus teks dengan satu tanda bintang atau garis bawah di setiap sisi.

    **teks tebal** atau __teks tebal__
    *teks miring* atau _teks miring_
    ***tebal dan miring***

<h4>Daftar List</h4>
 Daftar tidak berurutan menggunakan tanda minus (-), tanda bintang (*), atau tanda tambah (+). Daftar berurutan menggunakan angka diikuti titik (1., 2.,dst).

**a. List tidak berurutan (bullet)**

    - Item 1
    * Item 2
    + item 3

**b. List berurutan (angka)**

    1. Langkah pertama
    2. Langkah kedua
    1. Sub-langkah

<h4>5. Link dan Gambar</h4>
**a. Link**

Link dibuat dengan membungkus teks tautan dalam tanda kurung siku [] dan URL dalam tanda kurung biasa ()

    [OpenAI](https://openai.com)

**b. Gambar**

Dengan menggunakan tanda seru (!), diikuti dengan tanda kurung siku berisi teks alternatif (alt text), dan tanda kurung biasa berisi URL atau jalur ke gambar tersebut

    * !
    * [Teks Alt]
    *(URL gambar)

<h4> Code (Kode)</h4>
**a. Inline code**

Contoh menggunakan `console.log()` di JavaScript.

**b. Code block**

    Pakai 3 backtick ` ``` ` di atas dan bawah kode.
    ```javascript
    function halo() {
    console.log("Halo Dunia!");
    }
    ```
<h4>Quote (Kutipan)</h4>

    Menggunakan karakter > di awal setiap baris kutipan. 

    > Ini adalah contoh kutipan.

<h4>Garis Pemisah</h4>

Untuk membuat garis pemisah (horizontal rule) dalam Markdown, gunakan tiga atau lebih tanda hubung (-), tanda bintang (*), atau garis bawah (_) di satu baris

        ---
        ***
        ___