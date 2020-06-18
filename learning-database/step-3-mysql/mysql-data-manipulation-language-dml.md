# MySQL - Data Manipulation Language \(DML\)

DML merupakan istilah untuk beberapa sintaksis \(syntax\) dari SQL yang digunakan untuk melakukan perubahan pada data \(isi tabel-tabel\) dalam suatu database. DML terdiri dari 3 klausa utama yaitu:

1. INSERT : Menambah baris baru pada sebuah tabel
2. UPDATE : Mengubah nilai suatu baris pada sebuah tabel.
3. DELETE : Menghapus suatu baris dari sebuah tabel.

Pada DML terdapat dua jenis bahasa, yaitu :

1. High-Level\(Non\_procedural\) DML.
   * Digunakan secara interaktif \(interpreter\)
   * Dapat dijadikan satu dengan general purpose programming language \(embedded\)

     High-Level DML yang biasa digunakan secara interaktif disebut "Query Language".
2. Low-Level\(Proedural\) DML.

   Digunakan secara embedded dalam suatu general purpose programming language

Bilamana kedua jenis DML diatas digunakan secara "embedded", maka : bahasa pemrograman yang digunakan disebut sebagai "Host Language" dan "DML-nya disebut "Sub Language"

**Operasi INSERT**

Operasi insert bertujuan untuk menyisipkan satu tuple baru ke dalam suatu relasi R.

Klausa pembentuk:

1. `INSERT`
2. `INTO`
3. `VALUES`

Format:

1. `INSERT INTO nama_tabel (kolom1, kolom2, ...dst.) VALUES (nilai_kolom1, nilai_kolom2, ...dst.);`
2. `INSERT INTO nama_tabel VALUES (nilai_kolom1, nilai_kolom2, ...dst.);`
3. `[Salah satu dari kedua format sebelumnya], (nilai_kolom_kolom_baris1), (nilai_kolom_kolom_baris2), ...dst.`

Operasi ini memungkinkan untuk melanggar empat jenis constraint sebagaimana dijelaskan berikut ini :

1. DOMAIN Constraint dapat dilanggar jika suatu nilai attribute yang diberikan tidak ada dalam domain yang berkorespondensi dengan attribute tadi.
2. KEY Constraint dapat dilanggar jika nilai key dalam tuple baru t sudah ada dalam tuple lain dalam relasi r\(R\).
3. ENTITY INTEGRITY Constraint dapat dilanggar jika primary key dari tuple baru t adalah NULL
4. REFERENTIAL INTEGRITY Constraint dapat dilanggar jika nilai dari suatu foreign key dalam t mengacu ke suatu tuple yang tidak ada dalam relasi yang diacu.

Ada dua pilihan tindakan yang dapat dilakukan jika ada satu atau lebih constraint yang dilanggar akibat operasi insert, yaitu :

1. Menolak \(reject\) operasi insertion. Biasanya DBMS memberikan penjelasan mengapa proses insertion ditolak.
2. Berusaha memperbaiki alasan penolakan proses insertion. Dimana insertion akan diterima jika user melakukan perubahan nilai-nilai attribute sehingga insertion diterima.

**Operasi DELETE**

Operasi delete bertujuan untuk menghapus satu atau beberapa tuple di dalam suatu relasi R. Operasi ini hanya dapat melanggar referential integrity, jika tuple yang dihapus diacu oleh kunci-kunci tamu dari tuple yang lain dalam basis data.

Klausa pembentuk:

1. `DELETE`
2. `FROM`
3. `WHERE [opsional]`

Format:

1. `DELETE FROM nama_tabel WHERE nama_kolom_patokan [operator_perbandingan] nilai_patokan;`
2. `DELETE * FROM nama_tabel; atau DELETE FROM nama_tabel;`

Operator perbandingan/comparison operator dapat berupa: `=, <, >, <=, >=, <>`

Ada empat pilihan tindakan yang dapat dilakukan jika suatu deletion melanggar constraint yang telah ditentukan, yaitu :

1. Menolak\(reject\) proses deletion.
2. Berusaha untuk melakukan “cascade deletion”, yaitu dengan menghapus sejumlah tuple yang mengacu pada tuple yang akan dihapus.
3. Melakukan modifikasi nilai attribute yang mengacu pada tuple yang dihapus, yaitu setiap nilai diset NULL atau diganti dengan nilai dari tuple lain yang valid sebagai acuan baru. Akan tetapi, bila attribute yang mengacu yang menyebabkan pelanggaran adalah bagian dari primary key, maka ia tidak dapat diset NULL \(karena melanggar entity integrity\).
4. Kombinasi 2 dan 3.

**Operasi UPDATE**

Operasi update digunakan untuk merubah nilai-nilai satu atau lebih attribute dalam satu atau lebih tuple dalam sejumlah relasi R.

Klausa pembentuk:

1. `UPDATE`
2. `SET`
3. `WHERE [opsional]`

Format:

1. `UPDATE nama_tabel SET nama_kolom = nilai_baru WHERE nama_kolom_patokan [operator_perbandingan] nilai_patokan;`
2. `UPDATE nama_tabel SET nama_kolom1 = nilai_baru1, nama_kolom2 = nilai_baru2, ...dst. WHERE nama_kolom_patokan [operator_perbandingan] nilai_patokan;`

Operator perbandingan/comparison operator dapat berupa: `=, <, >, <=, >=, <>`

Operasi UPDATE bisa dilakukan pada tiga jenis attibut, dengan permasalahan yang berbeda sebagaimana berikut ini :

1. Modifikasi nilai suatu foreign key, maka DBMS harus melakukan pengecekan bahwa nilai-nilai baru yang diberikan mengacu pada tuple yang ada dalam relasi-relasi yang dijadikan acuan.
2. modifikasi nilai suatu primary key serupa dengan proses deletion satu tuple dan inserting yang lain pada tempat yang sama. Akibatnya, pilihan- pilihan seperti yang dilakukan pada operasi INSERT dan DELETE dapat dipakai agar modifikasi tidak melanggar constraint.
3. modifikasi suatu attribute yang bukan primary key atau bukan foreign key biasanya tidak akan menimbulkan masalah. DBMS hanya perlu untuk mengecek apakah nilai-nilai baru yang diberikan mempunyai tipe data dan domain yang valid.

### Praktikum – Bagian 1: Membuat Database untuk Percobaan <a id="praktikum-&#x2013;-bagian-1-membuat-database-untuk-percobaan"></a>

1. Perhatikan skema/model relasional/EER diagram dari database berikut.

   ![](https://data.sinaungoding.com/09/images/image002.png)

2. Skema tersebut adalah sekema database pada sebuah sistem informasi yang digunakan oleh suatu perusahaan yang bergerak di bidang pembuatan perangkat lunak. Pertama-tama, buatlah database tersebut dengan mengeksekusi baris-baris kode DDL berikut.

   ![](https://data.sinaungoding.com/09/images/image003.png)

   ![](https://data.sinaungoding.com/09/images/image004.png)

   ![](https://data.sinaungoding.com/09/images/image005.png)

   ![](https://data.sinaungoding.com/09/images/image006.png)

   ![](https://data.sinaungoding.com/09/images/image007.png)

3. Cek database Anda dengan perintah ‘SHOW TABLES’ untuk memastikan bahwa semua tabel sudah dibuat.

   ![](https://data.sinaungoding.com/09/images/image008.png)

4. Buat 1 tabel backup untuk tabel departemen bernama departemen\_backup. Tabel ini akan bermanfaat ketika bagian INSERT dan DELETE kita kerjakan.

   ![](https://data.sinaungoding.com/09/images/image009.png)

5. Cek strukturnya.

   ![](https://data.sinaungoding.com/09/images/image010.png)

6. Setelah selesai membuat database diatas, lanjutkan ke **Praktikum – Bagian 2.**

### Praktikum – Bagian 2: Percobaan Statement INSERT <a id="praktikum-&#x2013;-bagian-2-percobaan-statement-insert"></a>

1. Untuk menambahkan data \(mengisi\) suatu tabel, digunakan statement \(pernyataan\) INSERT. Eksekusi SQL berikut untuk menambahkan 1 baris \(record\) baru pada tabel departemen.

   ![](https://data.sinaungoding.com/09/images/image011.png)

2. Statement SQL tersebut menambahkan 1 baris baru ke tabel departemen pada kolom yang dinyatakan di dalam tanda kurung \(\) pertama. Untuk melihat hasil SQL yang kita eksekusi tersebut, gunakan statement SELECT seperti berikut.

   ![](https://data.sinaungoding.com/09/images/image012.png)

3. Pembahasan lebih lengkap mengenai SELECT dijadwalkan untuk disampaikan pada pertemuan berikutnya, namun secara umum, statement SELECT digunakan untuk menyajikan record-record yang ada pada suatu tabel. Karakter \* akan menampilkan isi dari semua kolom yang ada pada tabel. Statement SELECT tersebut menghasilkan:

   ![](https://data.sinaungoding.com/09/images/image013.png)

4. Apabila data di-insert-kan pada semua kolom tabel, maka kita dapat langsung menggunakan klausa VALUES tanpa harus menuliskan nama-nama kolom dahulu.

   ![](https://data.sinaungoding.com/09/images/image014.png)

5. Untuk menambahkan beberapa kolom sekaligus dalam 1 statement digunakan statement dengan format seperti berikut.

   ![](https://data.sinaungoding.com/09/images/image015.png)

6. Dan seperti berikut, jika hanya kolom tertentu saja yang akan diberi nilai.

   ![](https://data.sinaungoding.com/09/images/image016.png)

   ![](https://data.sinaungoding.com/09/images/image017.png)

   ![](https://data.sinaungoding.com/09/images/image018.png)

7. Statement INSERT juga dapat dieksekusi dengan menggunakan klausa SET alih-alih VALUES.

   ![](https://data.sinaungoding.com/09/images/image019.png)

   ![](https://data.sinaungoding.com/09/images/image020.png)

8. Pada statement INSERT juga dapat digunakan klausa SELECT. Misalnya kita ingin menyalin semua baris pada tabel departemen ke tabel departemen\_backup, maka kita SQL berikut dapat digunakan.

   ![](https://data.sinaungoding.com/09/images/image021.png)

   ![](https://data.sinaungoding.com/09/images/image022.png)

9. Sekarang penambahan data pada tabel karyawan dapat dilakukan karena data departemen sudah siap. Eksekusi SQL berikut ini untuk menambahkan beberapa data pegawai.

   ![](https://data.sinaungoding.com/09/images/image023.png)

   ![](https://data.sinaungoding.com/09/images/image024.png)

10. Setelah berhasil mengeksekusi SQL tersebut, lanjutkan ke **Praktikum - Bagian 3.**

### Praktikum - Bagian 3: Percobaan Statement UPDATE <a id="praktikum---bagian-3-percobaan-statement-update"></a>

1. UPDATE digunakan untuk mengubah nilai suatu baris pada sebuah tabel. Format dasar statement ini adalah sebagai berikut:

   ![](https://data.sinaungoding.com/09/images/image025.png)

2. Statement tersebut mengubah nilai SEMUA baris dari tabel departemen pada kolom nik\_manajer dengan nilai 741104013. Apabila kita tampilkan isi tabel, maka sekarang semua manajer akan dikepalai oleh karyawan dengan nik tersebut.

   ![](https://data.sinaungoding.com/09/images/image026.png)

3. Untuk mengubah nilai pada baris tertentu saja, kita tambahkan klausa WHERE pada statement UPDATE. Misalkan kita akan menjadikan karyawan dengan nip 7411040719 sebagai manajer pada departemen PKU, maka dapat digunakan SQL sebagai berikut:

   ![](https://data.sinaungoding.com/09/images/image027.png)

   ![](https://data.sinaungoding.com/09/images/image028.png)

4. Klausa WHERE tidak selalu hanya membatasi UPDATE pada 1 baris saja, ia juga bisa memberlakukan UPDATE pada banyak baris sekaligus. Semuanya tergantung pada kondisi yang kita tentukan. Statement berikut ini akan mengosongkan nik\_manajer untuk semua departemen yang dikepalai oleh karyawan dengan nik 741104013.

   ![](https://data.sinaungoding.com/09/images/image029.png)

   ![](https://data.sinaungoding.com/09/images/image030.png)

5. Untuk mengubah beberapa kolom sekaligus dalam satu kali eksekusi statement UPDATE, dapat digunakan format berikut.

   ![](https://data.sinaungoding.com/09/images/image031.png)

   ![](https://data.sinaungoding.com/09/images/image032.png)

6. Kita juga dapat menggunakan statement UPDATE dengan SELECT. Misalkan kita ingin mengeset nik\_manajer departemen ‘RND’ dengan nik karyawan yang bernama ‘Ahmad Husain’, maka dapat digunakan SQL dengan format berikut.

   ![](https://data.sinaungoding.com/09/images/image033.png)

   ![](https://data.sinaungoding.com/09/images/image034.png)

7. Setelah berhasil mengeksekusi SQL tersebut, lanjutkan ke **Praktikum - Bagian 4.**

### Praktikum - Bagian 4: Percobaan Statement DELETE <a id="praktikum---bagian-4-percobaan-statement-delete"></a>

1. DELETE digunakan untuk menghapus satu atau lebih baris dari sebuah tabel. Misalkan kita ingin menghapus departemen yang memiliki nilai pada kolom nik\_manajernya, maka format dasar statement seperti berikut dapat kita gunakan:

   ![](https://data.sinaungoding.com/09/images/image035.png)

   ![](https://data.sinaungoding.com/09/images/image036.png)

2. HATI-HATI apabila kita menggunakan statement DELETE tanpa WHERE! Cobalah eksekusi syntax SQL berikut:

   ![](https://data.sinaungoding.com/09/images/image037.png)

3. Semua data dalam satu tabel departemen akan hilang!

   ![](https://data.sinaungoding.com/09/images/image038.png)

