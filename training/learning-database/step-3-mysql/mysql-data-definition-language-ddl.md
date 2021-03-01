# MySQL - Data Definition Language \(DDL\)

**Basis Data:** Himpunan kelompok data \(arsip\) yang saling berhubungan, yang diorganisasi sedemikan rupa, sehingga kelak dapat dimanfaatkan kembali dengan cepat.

Bahasa Basis Data

DBMS merupakan perantara antara user dengan database. Cara komunikasi diatur dalam suatu bahasa khusus yang ditetapkan oleh DBMS. Misalnya SQL,dBase,QUEL, dsb. Ada beberapa bentuk bahasa sql, namun yang biasa digunakan adalah 2 bentuk bahasa sql yaitu DDL dan DML

Data Definition Language \(DDL\) &gt;&gt; digunakan dalam membuat tabel baru, indeks, mengubah tabel, menentukan struktur tabel, dsb

Data Manipulation Language \(DML\) &gt;&gt; digunakan dalam memanipulasi dan pengambilan data pada database. Manipulasi data dapat mencakup :

* Pemanggilan data yang tersimpan dalam database \(query\)
* Penyisipan/penambahan data baru ke database
* Penghapusan data dari database
* Pengubahan data pada database

**Dasar-Dasar MySQL**

Dalam bahasa SQL pada umumnya informasi tersimpan dalam tabel-tabel yang secara logik merupakan struktur dua dimensi terdiri dari baris \(row atau record\) dan kolom \(column atau field\). Sedangkan dalam sebuah database dapat terdiri dari beberapa table. Beberapa tipe data dalam MySQL yang sering dipakai:

![](https://data.sinaungoding.com/08/images/01.png)

Data Definition Language \(DDL\) merupakan sekumpulan set perintah yang bertujuan untuk mendefinisikan atribut-atribut database, tabel, atribut kolom \(field\), maupun batasan-batsan terhadap suatu atribut dan relasi/ hubungan antar tabel. Yang termasuk dalam kelompok perintah DDL adalah :

* `Create`
* `Alter`
* `Drop`

**CREATE** merupakan perintah DDL yang digunakan untuk membuat database maupun tabel. Nama database maupun tabel tidak boleh mengandung spasi \(space\). Nama database tidak boleh sama antar database.

**ALTER** merupakan perintah DDL yang digunakan untuk mengubah nama/struktur tabel

**DROP** merupakan perintah DDL yang digunakan untuk menghapus database ataupun tabel

a. Database

Perintah untuk membuat database sebagai berikut :

* `CREATE DATABASE namadatabase;`

  Contoh :

  `CREATE DATABASE db_polinema;`

  Untuk menampilkan daftar nama database yang terdapat dalam database server pada MySQL menggunakan perintah :

* `SHOW DATABASES;`

  Sebelum membuat suatu tabel yang akan digunakan untuk menyimpan data, terlebih dahulu harus memilih/mengaktifkan salah satu database sebagai database aktif yang akan digunakan untuk menyimpan beberapa tabel yang akan dibuat. Untuk memilih/mengaktifkan salah satu database menggunakan perintah berikut :

* `USE namadatabase;`

  Sebagai contoh, database db\_polinema yang akan digunakan / diaktifkan maka perintahnya sebagai berikut:

  `USE db_polinema;`

  Perintah yang berfungsi untuk menghapus database maupun tabel adalah perintah DROP. Untuk menggunakan perintah tersebut, berikut penulisan perintahnya :

* `DROP DATABASE namadatabase;`

  Misalnya database db\_polinema yang akan dihapus maka perintahnya sebagai berikut :

  `DROP DATABASE db_polinema;`

b. Tabel

* Membuat Tabel

  Nama tabel tidak boleh mengandung spasi \(space\). Ketika membuat tabel, ada beberapa yang harus dideklarasikan dalam pembuatannya yaitu antara lain meliputi : nama tabel, nama kolom \(field\), tipe data dari field dan panjang data. Perintah yang digunakan untuk membuat tabel secara umum adalah sebagai berikut :

  `CREATE TABLE namatabel (field1 typedata1, field2 typedata2);` Contoh berikut ini adalah syntax untuk membuat tabel mahasiswa :

  ```text
  `CREATE TABLE mahasiswa (nim CHAR (20),nama_mhs CHAR(50),umur INT, PRIMARY KEY(nim));`
  ```

* Menampilkan tabel Untuk menampilkan daftar nama tabel yang terdapat dalam database yang sedang aktif/digunakan menggunakan perintah :

  `SHOW TABLES;`

* Menampilkan deskripsi atribut tabel

  Untuk menampilkan deskripsi atribut-atribut yang terdapat pada suatu tabel dengan menggunakan perintah :

  `DESC namatabel;`

  Contoh: `DESC mahasiswa;`

* Menghapus Tabel

  Untuk menghapus Tabel perintahnya sama dengan untuk menghapus database yaitu dengan menggunakan perintah DROP. Perintah yang digunakan adalah :

  `DROP TABLE namatabel;`

  Misalnya yang akan dihapus adalah tabel mahasiswa :

  `DROP TABLE mahasiswa;`

* Mengisi Data Untuk memasukkan sebuah baris \(record\) kedalam tabel MySQL adalah sebagai berikut :

  `INSERT INTO table [(column1, column2,...) VALUES (value1, value2,...)];`

  Contoh : `Insert into mahasiswa (nim,nama,umur) values (‘001’,’imam’,20);`

* Mendefinisikan Null/Not Null

  Null ataupun Not Null merupakan pernyataan yang digunakan untuk membuat kolom yang akan dibuat boleh kosong \(Null\) atau tidak boleh kosong \(Not Null\). Ketika pada kolom tabel tidak di set, maka secara default akan bernilai Null \(boleh kosong\). Untuk mendefinisikannya maka perintah yang akan digunakan adalah :

  `CREATE TABLE mahasiswa (nim CHAR (20) NOT NULL, nama_mhs CHAR (50) NOT NULL, umur INT, PRIMARY KEY (nim));`

* Mendefinisikan Nilai Default Nilai default merupakan nilai yang diberikan secara otomatis oleh sistem untuk suatu kolom ketika terjadi penambahan baris baru, sementara nilai pada kolom tersebut tidak diisi oleh pengguna.

  Contoh : `CREATE TABLE mahasiswa (nim CHAR (20), nama-mhs CHAR (50), umur INT DEFAULT 0, PRIMARY KEY (nim));`

* Mendefinisikan PRIMARY KEY pada Tabel

  Suatu keharusan dalam suatu tabel adalag harus memiliki satu kolom yang dijadikan sebagai perwakilan dari tabel tersebut. Pembuatan perwakilan tabel ini berfungsi untuk melakukan hubungan / relasional dengan tabel lain. Bentuk perwakilan ini dalam database disebut sebagai PRIMARY KEY yang aturan pembuatannya adalah sebagai berikut :

  * Satu tabel bisa memiliki 2 primary key
  * Nama kolom kunci tidak digunakan pada kolom lain satu tabel
  * Nama kolom kunci tidak boleh sama dengan kolom kunci yang ada pada tabel lain
  * Bentuk kolom kunci harus diset NOT NULL

    Terdapat tiga cara untuk mendefinisikan primary key. Berikut ini perintah yang digunakan :

    `CREATE TABLE mahasiswa (nim CHAR (20), nama_mhs CHAR (50), umur INT, PRIMARY KEY (nim));`

    Atau `CREATE TABLE mahasiswa (nim CHAR (20) NOT NULL PRIMARY KEY, nama_mhs CHAR (50), umur INT);`

    Atau `ALTER TABLE mahasiswa ADD CONSTRAINT namaconstraint PRIMARY KEY(namakolom);`

* Menghapus PRIMARY KEY pada tabel

  Cara 1: Jika primary key dibuat menggunakan alter table: `ALTER TABLE namatabel DROP CONSRTRAINT namaconstraint;`

  Cara 2: Jika primary key dibuat melalui create table: `ALTER TABLE namatable DROP PRIMARY KEY;`

* Menambah kolom baru pada tabel

  Untuk menambah kolom baru pada suatu tabel bisa menggunakan perintah sebagai berikut :

  `ALTER TABLE namatabel ADD fieldbaru typedata(lebar);`

  Namatabel merupakan nama tabel yang akan ditambahkan kolomnya. Filedbaru merupakan nama kolom yang akan ditambahkan, typedata\(lebar\) merupakan type data dan lebar data yang akan ditambahkan. Contohnya menambahkan kolom telepon pada tabel mahasiswa setelah kolom umur:

  `ALTER TABLE mahasiswa ADD COLUMN telepon CHAR (15) AFTER umur;`

* Mengubah Tipe Data atau Lebar Kolom pada Tabel

  Perintah yang digunakan adalah :

  `ALTER TABLE namatabel MODIFY COLUMN field type(lebar);`

  Contoh : `ALTER TABLE mahasiswa MODIFY COLUMN telepon(12);`

* Mengubah Nama Kolom\(Field\) Perintah yang digunakan adalah :

  `ALTER TABLE namatabel CHANGE COLUMN namakolomlama namakolombaru typedatabaru(lebarbaru);`

  Contoh : `ALTER TABLE mahasiswa CHANGE COLUMN telepon phone CHAR(25);`

* Menghapus Kolom pada Tabel

  Perintah yang digunakan adalah :

  `ALTER TABLE namatabel DROP COLUMN namakolom;`

  Contoh : `ALTER TABLE mahasiswa DROP COLUMN phone;`

* Mendefinisikan Foreign Key

  Foreign Key adalah salah satu jenis constraint yang digunakan untuk merelasikan antar dua tabel atau lebih. Foreign Key digunakan pada tabel kedua \(detail\) yang mereferensi ke tabel utama yang mempunyai constraint primary key.

  ![](https://data.sinaungoding.com/08/images/02.png)

  Pada gambar diatas, kolom Cust\_ID pada tabel Orders berperan sebagai foreign key yang mereferensi ke tabel Customers pada kolom ID.

  `ALTER TABLE namatabel ADD FOREIGN KEY namafield REFERENCES namatabelreferensi (namafieldreferensi);`

