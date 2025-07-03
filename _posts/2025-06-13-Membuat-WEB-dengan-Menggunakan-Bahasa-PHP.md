---
layout: post 
title: "Membuat WEB dengan Menggunakan Bahasa PHP"
---

Materi Membuat website menggunakan bahasa PHP

**Langkah-Langkah Membuat website menggunakan bahasa PHP**

1. Buka XAMPP untuk menjalankan "APACHE" dan "MYSQL"

2. Buka folder htdocs di dalam folder XAMPP

3. Cari folder "htdocs" dan buka

4. Buat folder baru di dalam htdocs dengan nama "latihan"

5. Lalu buka di Visual Studio Code dengan cara klik kanan difolder “Latihan” pilih "Open Git Bush here", lalu akan muncul terminal, ketik "code ." dalam terminal tersebut

6. Seeblum menlanjutkannya, buat database latihan terlebih dahulu agar dapat dipanggil menggunakan bahasa php

7. Pertama buka XAMPP lalu klik "Admin" dibarisan bagian "MySQL"

8. Ketik "CREATE DATABASE latihan"

9. Lalu pilih "SQL" lagi, ketik "create table siswa ( id int auto_increment primary key, nama varchar(100), alamat varchar(200), jenis_kelamin tinyint(1), agama varchar(20), sekolah_asal varchar(50));

10. Setelah itu kita kembali lagi ke Visual Studio Code buat file baru dengan nama “create.php”, lalu isi dengan kode seperti dibawah ini :

        <?php

            include "koneksi.php";
                
            $nama = $_POST['nama'];
            $alamat = $_POST['alamat'];
            $jenis_kelamin = $_POST['jenis_kelamin'];
            $agama = $_POST['agama'];
            $sekolah_asal = $_POST['sekolah_asal'];
                
            $sql = "INSERT INTO siswa (nama, alamat, jenis_kelamin, agama, sekolah_asal)
                    VALUES ('$nama', '$alamat', '$jenis_kelamin', '$agama', '$sekolah_asal')";
                
            if (mysqli_query($koneksi, $sql)) {
                header("location: list-siswa.php");
            } else {
                echo "Error: " . $sql . "<br>" . mysqli_error($koneksi);
            }
                
        ?>

11. Setelah itu buat file "koneksi.php" untukm menarik dari file database dari "MySQL". Isi dengan :

        <?php
            
        $host = 'localhost';
        $username = 'root';
        $password = '000';
        $db_name = 'latihan';
            
        $koneksi = mysqli_connect($host, $username, $password, $db_name);
            
        if (!$koneksi){
            die("koneksi gagal: " . mysqli_connect_error());
        }
            
        ?>

12. Lalu buat file dengan nama "delete.php". Isi dengan :
        <?php
            
        include "koneksi.php";
            
        $id = $_POST['id'];
            
        $sql = "DELETE FROM siswa WHERE id=$id";
            
        if (mysqli_query($koneksi, $sql)) {
            header("location:list-siswa.php");
        } else {
            echo "Error deleting record: " . mysqli_error($koneksi);
        }

13. Kemudian buat lagi file baru dengan nama “form-daftar.php”

        <!DOCTYPE html>
        <html lang="en">
            
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Form Pendaftaran Siswa Baru | Digital Talent</title>
        </head>
            
        <body>
            <h2>Formulir Pendaftaran Siswa Baru</h2>
            <form action="create.php" method="POST">
                <table>
                    <tr>
                        <td>Nama</td>
                        <td>:</td>
                        <td><input type="text" name="nama"></td>
                    </tr>
                    <tr>
                        <td>Alamat</td>
                        <td>:</td>
                        <td>
                            <input type="radio" name="jenis_kelamin" value="1"> Laki-laki
                            <input type="radio" name="jenis_kelamin" value="0"> Perempuan
                        </td>
                    </tr>
                    <tr>
                        <td>Agama</td>
                        <td>:</td>
                        <td>
                            <select name="agama">
                                <option>--Pilih Agama--</option>
                                <option>Islam</option>
                                <option>Kristen</option>
                                <option>Hindu</option>
                                <option>Buddha</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td>Sekolah Asal</td>
                        <td>:</td>
                        <td><input type="text" name="sekolah_asal"><br/></td>
                    </tr>
                    <tr>
                        <td colspan="2">
                        </td>
                        <td>
                            <button type="submit">Daftar</button>
                            <a href="index.php">Batal</a>
                        </td>
                    </tr>
                </table>
            </form>
        </body>
        </html>

14. Kemudian file dengan nama “form-delete.php”

        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Form Hapus Siswa</title>
        </head>
        <body>
            
        <?php
            include "koneksi.php";
            $id = $_GET['id'];
            $sql = "SELECT * FROM siswa WHERE id=$id";
            $result = mysqli_query($koneksi, $sql);
            $row = mysqli_fetch_assoc($result);
            ?>
            
        <h2>Apakah Anda yakin akan menghapus data berikut?</h2>
        <form action="delete.php" method="POST">
            <input type="hidden" name="id" value="<?php echo $row['id'] ?>">
            Nama : <?php echo $row['nama'] ?> <br/>
            Jenis Kelamin :
            <?php
                if ($row['jenis_kelamin'] == 1) {
                    echo "Laki-laki";
                } else {
                    echo 'Perempuan';
                }
                ?>
            Agama : <?php echo $row['agama'] ?> <br/>
            Sekolah Asal : <?php echo $row['sekolah_asal'] ?> <br/>
            <button type="submit">Ya</button>
            <a href="list-siswa.php">Tidak</a>
        </form>
        </body>
        </html>

15. Lalu file dengan nama "form-edit.php". Isi dengan

        <!DOCTYPE html>
        <html lang="en">
            
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Form Edit Siswa</title>
        </head>
            
        <body>
            
        <?php
            include "koneksi.php";
            $id = $_GET['id'];
            $sql = "SELECT * FROM siswa WHERE id=$id";
            $result = mysqli_query($koneksi, $sql);
            $row = mysqli_fetch_assoc($result);
            ?>
            
        <h2>Formulir Edit Siswa</h2>
        <form action="update.php" method="POST">
            <input type="hidden" name="id" value="<?php echo $row['id'] ?>">
            Nama :
            <input type="text" name="nama" value="<?php echo $row['id'] ?>"> <br />
            Alamat :
            <textarea name="alamat">
                <?php echo $row['alamat'] ?>
            </textarea> <br/>
            Jenis Kelamin :
            <input type="radio" name="jenis_kelamin" value="1" <?php if ($row['jenis_kelamin'] == 1) echo "checked" ?>>
            Laki-laki
            <input type="radio" name="jenis_kelamin" value="0" <?php if ($row['jenis_kelamin'] == 0) echo "checked" ?>>
            Perempuan <br/>
            Agama :
            <select name="agama">
                <option>--Pilih Agama</option>
                <option value="Islam"></option>
                <option value="Kristen"></option>
                <option value="Hindu"></option>
                <option value="Buddha"></option>
            </select> <br/>
            Sekolah asal :
            <input type="text" name="sekolah_asal" value="<?php echo $row['sekolah_asal'] ?>">
            <br/>
            <button type="submit">Update</button>
            <a href="list-siswa.php">Batal</a>
        </form>
        </body>
        </html>

16. Lalu file “index.php” dengan isi 

        <?php
            
        echo "<h2> Pendaftaran Siswa Baru</h2>
            
            <h1>Digital Talent</h1>
            
            <h3>Menu</h3>
            
            <li><a href='form-daftar.php'>Daftar Baru</a></li>
            <li><a href='list-siswa.php'>Pendaftaran</a></li>
            </ul>";
            
        ?>

17. Lalu file “list-siswa.php” dengan isi 

        <!DOCTYPE html>
        <html lang="en">
            
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Daftar Siswa</title>
        </head>
            
        <body>
        <h2>Siswa yang sudah mendaftar</h2>
            
        <ul>
            <li><a href="index.php">Home</a></li>
            <li><a href="form-daftar.php">[+] Tambah Baru</a></li>
        </ul>
            
        <?php
            include "koneksi.php";
            
            $sql = "SELECT * FROM siswa";
            $result = mysqli_query($koneksi, $sql);
            ?>
        <table border="1">
            <thead>
            <tr>
                <th>No</th>
                <th>Nama</th>
                <th>Alamat</th>
                <th>Jenis Kelamin</th>
                <th>Agama</th>
                <th>Sekolah Asal</th>
                <th>Tindakan</th>
            </tr>
            </thead>
            <tbody>
            <?php
                    $no = 1;
                    while ($row = mysqli_fetch_assoc($result)) {
                        ?>
            <tr>
                <td><?php echo $no++; ?></td>
                <td><?php echo $row['nama']; ?></td>
                <td><?php echo $row['alamat']; ?></td>
                <td>
                    <?php
                                if ($row['jenis_kelamin'] == 1) {
                                    echo "Laki-laki";
                                } else {
                                    echo "Perempuan";
                                }
                                ?>
                </td>
                <td><?php echo $row['agama']; ?></td>
                <td><?php echo $row['sekolah_asal']; ?></td>
                <td>
                    <a href="form-edit.php?id=<?php echo $row['id']; ?>">Edit</a>
                    <a href="form-delete.php?id=<?php echo $row['id']; ?>">Delete</a>
                </td>
            </tr>
            <?php
                    }
                ?>
            </tbody>
        </table>
    
18. Lalu buat file “update.php” dengan isi : 
        <?php
            
        include "koneksi.php";
            
        $id = $_POST['id'];
        $nama = $_POST['nama'];
        $alamat = $_POST['alamat'];
        $jenis_kelamin = $_POST['jenis_kelamin'];
        $agama = $_POST['agama'];
        $sekolah_asal = $_POST['sekolah_asal'];
            
        $sql = "UPDATE siswa SET nama='$nama', alamat='$alamat', jenis_kelamin='$jenis_kelamin', agama='$agama', sekolah_asal='$sekolah_asal' WHERE id=$id";
            
        if (mysqli_query($koneksi, $sql)) {
            header("location:list-siswa.php");
        } else {
            echo "Error updating record: " . mysqli_error($koneksi);
        }
            
        ?>