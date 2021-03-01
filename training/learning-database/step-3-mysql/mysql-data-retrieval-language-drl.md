# MySQL - Data Retrieval Language \(DRL\)

DRL atau DSL \(Data Selection Language\) adalah set perintah yang dgunakan untuk mengambil data dari server basis data. DRL terdiri dari klausa yang dapat dikembangkan lebih lanjut, antara lain:

1. `FROM`: Memilih nama sebuah tabel
2. `WHERE`: Menunjukkan secara spesifik suatu row/baris yang akan dicari
3. `GROUP BY`: Menyusung data ke dalam grup
4. `HAVING`: Memilih diantara kelompok-kelompok data yang didefinisikan klausa GROUP BY
5. `ORDER BY`: Secara spesifik digunakan untuk menentukan suatu baris pada kolom tertentu
6. `AS`: Memberikan nama alias sementara untuk tabel atau kolom

DRL lebih diterapkan dalam beberapa hal dalam beberapa hal seperti :

1. `QUERY`
2. `SUB-QUERY`
3. `FUNGSI AGREGASI`

#### Query <a id="query"></a>

Query merupakan operasi yang melibatkan satu atau lebih tabel untuk melakukan retrival data. Pengambilan data dilakukan dengan beberapa klausa berikut :

1. `SELECT *` untuk memilih semua kolom Format

   ```text
     SELECT * FROM table_name;
   ```

2. `SELECT` dengan `WHERE` untuk menampilkan baris dengan suatu kondisi

   Format

   ```text
     SELECT column1, column2,...
     FROM table_name
     WHERE condition;
   ```

3. `SELECT` dengan `DISTINCT` untuk menampilkan data dengan eliminasi data yang sama \(duplicate\)

   Format

   ```text
     SELECT DISTINCT column FROM table_name;
   ```

4. `SELECT` dengan `IN` untuk menampilkan data yang spesifik

   Format

   ```text
     SELECT column_name(s)
             FROM table_name
             WHERE column_name IN (value1, value2, ...);
   ```

5. `SELECT` dengan `BETWEEN` untuk menampilkan data pada jarak \(range\) tertentu

   Format

   ```text
     SELECT column_name(s)
             FROM table_name
             WHERE column_name BETWEEN value1 AND value2;
   ```

6. `SELECT` dengan `LIKE` untuk menampilkan data yang memiliki kemiripan dengan keyword yang diinginkan

   Format

   ```text
     SELECT column1,column2,...
             FROM table_name
             WHERE columnN LIKE pattern;
   ```

7. `SELECT` dengan `GROUP BY` untuk menampilkan susunan data dalam bentuk grup

   Format

   ```text
     SELECT column1, column2,...
             condition
             FROM table_name
             GROUP BY column1, column2, ...;
   ```

8. `SELECT` dengan `ORDER BY` untuk menampilkan baris secara spesifik dan terurut maju atau mundur

   Format

   ```text
     SELECT column1, column2, ...
             FROM table_name
             ORDER BY column1, column2, ... ASC|DESC;
   ```

9. `SELECT` dengan`AND, OR and NOT` untuk menampilkan data dengan kondisi dan atau atau tidak

   Format

   `AND`

   ```text
     SELECT column1, column2, ...
             FROM table_name
             WHERE condition1 AND condition2 AND condition3 ...;
   ```

   `OR`

   ```text
     SELECT column1, column2, ...
             FROM table_name
             WHERE condition1 OR condition2 OR condition3 ...;
   ```

   `NOT`

   ```text
     SELECT column1, column2, ...
             FROM table_name
             WHERE NOT condition;
   ```

10. `SELECT` dengan `UNION, INTERSECT dan EXCEPT` untuk menampikan data dengan operasi himpunan yang melibatkan lebih dari satu tabel

    Format `UNION`

    Tanpa duplikasi

    ```text
     SELECT column_name(s) FROM table1
             UNION
             SELECT column_name(s) FROM table2;
    ```

    Dengan duplikasi

    ```text
     SELECT column_name(s) FROM table1
             UNION ALL
             SELECT column_name(s) FROM table2;
    ```

    `INTERSECT` Tanpa duplikasi

    ```text
     SELECT column_name(s) FROM table1
             INTERSECT
             SELECT column_name(s) FROM table2;
    ```

    Dengan duplikasi

    ```text
     SELECT column_name(s) FROM table1
             INTERSECT ALL
             SELECT column_name(s) FROM table2;
    ```

    `EXCEPT` Tanpa duplikasi

    ```text
     SELECT column_name(s) FROM table1
             EXCEPT
             SELECT column_name(s) FROM table2;
    ```

    Dengan duplikasi

    ```text
     SELECT column_name(s) FROM table1
             EXCEPT ALL
             SELECT column_name(s) FROM table2;
    ```

#### Sub Query <a id="sub-query"></a>

Sub-query adalah adanya query di dalam query lain. Sub-query juga disebut dengan perintah `SELECT` bersarang \(nested SELECT\). Retrival data dalam sub-query dilakukan oleh `SELECT` untuk menemukan data pada `SELECT` utama. Klausa `GROUP BY` dan `HAVING` juga dapat digunakan untuk retrival data pasa sub-query. Sub-query biasanya digunakan untuk test keanggotaan himpunan atau perbandingan himpunan dan kardinalitas. Format Untuk test keanggotaan

```text
SELECT column_name(s)
FROM table_name
WHERE column_name IN (SELECT STATEMENT);
```

atau

```text
SELECT column_name(s)
FROM table_name
GROUP BY column1, column2, ...;
HAVING column_name IN (SELECT STATEMENT);
```

Untuk perbandingan himpunan

```text
SELECT column_name(s)
FROM table_name 
operator
(SELECT STATEMENT);
```

#### Fungsi Agregasi <a id="fungsi-agregasi"></a>

Fungsi agregasi akan melakukan perhitungan kepada sekumpulan nilai dan menghasilkan suatu nilai tunggal.

Jenis:

1. `AVG` untuk menghitung rata-rata Format

   ```text
     SELECT AVG(column_name)
     FROM table_name
     WHERE condition;
   ```

2. `MAX` untuk mencari nilai tertinggi Format

   ```text
     SELECT MAX(column_name)
     FROM table_name
     WHERE condition;
   ```

3. `MIN` untuk mencari nilai terendah Format

   ```text
     SELECT MIN(column_name)
     FROM table_name
     WHERE condition;
   ```

4. `SUM` untuk menjumlahkan sekumpulan nilai Format

   ```text
     SELECT SUM(column_name)
     FROM table_name
     WHERE condition;
   ```

5. `COUNT()` untuk menunjukkan jumlah baris pada kolom yang diinginkan Format

   ```text
     SELECT COUNT(column_name)
     FROM table_name
     WHERE condition;
   ```

### Praktikum – Bagian 1: Membuat Database untuk Percobaan <a id="praktikum-&#x2013;-bagian-1-membuat-database-untuk-percobaan"></a>

1. Studi kasus yang digunakan sama dengan jobsheet DML dengan skema/model relasional/EER diagram dari database berikut.

   ![](https://data.sinaungoding.com/10/images/image002.png)

2. Skema tersebut adalah skema database pada sebuah sistem informasi yang digunakan oleh suatu perusahaan yang bergerak di bidang pembuatan perangkat lunak. Sesuai dengan percobaan pada jobsheet DML. Insert kembali departemen yang mengandung nama ‘dan’, dengan cara menyalin dari tabel departemen\_backup, sehingga menghasilkan record keseluruhan tabel sebagai berikut \(record tidak harus sama persis dengan tampilan ini\):

   `SELECT * FROM departemen;`

   ![](https://data.sinaungoding.com/10/images/image004.png)

   `SELECT * FROM karyawan;`

   ![](https://data.sinaungoding.com/10/images/image006.png)

   `SELECT * FROM klien;`

   ![](https://data.sinaungoding.com/10/images/image008.png)

   `SELECT * FROM proyek;`

   ![](https://data.sinaungoding.com/10/images/image010.png)

   `SELECT * FROM penugasan;`

   ![](https://data.sinaungoding.com/10/images/image012.png)

3. Setelah selesai membuat database diatas, lanjutkan ke Praktikum – Bagian 2.

### Praktikum – Bagian 2: Percobaan SELECT QUERY <a id="praktikum-&#x2013;-bagian-2-percobaan-select-query"></a>

1. Untuk menampilkan baris dengan suatu kondisi tertentu, digunakan statement SELECT dengan WHERE. Eksekusi SQL berikut untuk menampilkan \(record\) pada tabel karyawan yang memiliki kolom departemen\_kode=’MKT’.

   ```text
    SELECT nama 
    FROM karyawan 
    WHERE departemen_kode = 'MKT';
   ```

   ![](https://data.sinaungoding.com/10/images/image014.png)

2. Untuk menampilkan data dengan eliminasi data yang sama \(duplicate\), digunakan statement SELECT dengan DISTINCT. Eksekusi SQL berikut untuk menampilkan kolom total\_jam dari tabel penugasan yang bernilai tidak sama.

   ```text
    SELECT DISTINCT total_jam 
    FROM penugasan;
   ```

   ![](https://data.sinaungoding.com/10/images/image016.png)

3. Untuk menampilkan data yang spesifik digunakan statement SELECT dengan IN. Eksekusi SQL berikut untuk menampilkan kolom nim dan nik dari tabel karyawan yang memiliki gaji 3100000 atau 6900000.

   ```text
    SELECT nik, nama 
    FROM karyawan 
    WHERE gaji IN (3100000,6900000);
   ```

   ![](https://data.sinaungoding.com/10/images/image018.png)

4. Untuk menampilkan data pada jarak \(range\) tertentu digunakan statement SELECT dengan BETWEEN. Eksekusi SQL berikut untuk menampilkan kolom nik dan nama dari tabel karyawan yang memiliki gaji diantara 2000000 dan 4000000.

   ```text
    SELECT nik, nama 
    FROM karyawan 
    WHERE gaji 
    BETWEEN 2000000 AND 4000000;
   ```

   ![](https://data.sinaungoding.com/10/images/image020.png)

5. Untuk menampilkan data yang memiliki kemiripan dengan keyword yang diinginkan digunakan SELECT dengan LIKE. Eksekusi SQL berikut untuk menampilkan kolom nama, alamat, dan jenis pada tabel klien yang memiliki nama dengan huruf awal ‘a’.

   `SELECT nama, alamat, jenis FROM klien WHERE nama like 'a%';`

   ![](https://data.sinaungoding.com/10/images/image022.png)

6. Untuk menampilkan susunan data dalam bentuk grup, digunakan SELECT dengan GROUP BY. Eksekusi SQL berikut untuk menampilkan kolom nik, nama, gaji, dan departemen\_kode pada tabel karyawan yang dikelompokkan berdasarkan gaji.

   ```text
    SELECT nik, nama, gaji, departemen_kode 
    FROM karyawan 
    GROUP BY gaji;
   ```

   ![](https://data.sinaungoding.com/10/images/image024.png)

7. Untuk menampilkan baris secara spesifik dan terurut maju atau mundur, digunakan SELECT dengan ORDER BY. Eksekusi SQL berikut untuk menampilkan kolom nama dan tanggal\_mulai pada tabel proyek dari tanggal yang paling lama hingga baru.

   ```text
    SELECT nama, tanggal_mulai 
    FROM proyek 
    ORDER BY tanggal_mulai ASC;
   ```

   ![](https://data.sinaungoding.com/10/images/image026.png)

8. Untuk menampilkan data dengan kondisi dan atau atau tidak, digunakan SELECT dengan AND, OR and NOT. Eksekusi SQL berikut untuk menampilkan semua kolom pada tabel karyawan dengan jenis kelamin ‘WANITA’ dan gaji &lt; 5000000.

   ```text
    SELECT * 
    FROM karyawan 
    WHERE jenis_kelamin = 'WANITA' AND gaji < 5000000;
   ```

   ![](https://data.sinaungoding.com/10/images/image028.png)

9. Untuk menampilkan data dari kolom yang terlibat dalam dua tabel dapat digunakan SELECT dengan UNION. UNION secara otomatis akan menghilangkan duplikasi. Eksekusi SQL berikut untuk menampilkan kolom nik yang yang ada di tabel penugasan atau departemen.

   ```text
    SELECT nik 
    FROM penugasan 
    UNION ALL 
    SELECT nik_manajer FROM departemen;
   ```

   ![](https://data.sinaungoding.com/10/images/image030.png)

10. Untuk menampilkan data dari kolom yang terlibat dalam dua tabel dapat digunakan SELECT dengan UNION ALL. UNION ALL juga akan menampilkan duplikasi data. Eksekusi SQL berikut untuk menampilkan kolom nik yang yang ada di tabel penugasan atau departemen.

    ```text
    SELECT nik 
    FROM penugasan 
    UNION ALL 
    SELECT nik_manajer FROM departemen;
    ```

    ![](https://data.sinaungoding.com/10/images/image032.png)

11. Setelah berhasil mengeksekusi SQL tersebut, lanjutkan ke Praktikum - Bagian 3.

### Praktikum - Bagian 3: Percobaan SELECT Sub-Query <a id="praktikum---bagian-3-percobaan-select-sub-query"></a>

1. Untuk menampilkan data \(test keanggotaan sub-query\) yang berasal dari pemilihan tampilan data lain digunakan tambahan statement IN. Eksekusi SQL berikut untuk menampilkan kolom nomor\_proyek, nik, total\_jam pada tabel penugasan dimana total\_jam adalah total\_jam yang paling lama pada tabel penugasan.

   ```text
    SELECT nomor_proyek, nik, total_jam 
    FROM penugasan 
    WHERE total_jam 
    in (SELECT MAX(total_jam) FROM penugasan);
   ```

   ![](https://data.sinaungoding.com/10/images/image034.png)

2. Untuk menampilkan data \(perbandingan himpunan sub-query\) yang berasal dari pemilihan tampilan data lain digunakan tambahan operator. Eksekusi SQL berikut untuk menampilkan kolom nomor\_proyek, nik, total\_jam pada tabel penugasan berdasarkan semua record kolom total\_jam harus bernilai kurang dari total\_jam yang dimiliki oleh nomor proyek 1 dari tabel penugasan.

   ```text
    SELECT nomor_proyek, nik, total_jam 
    FROM penugasan 
    WHERE total_jam < ALL (SELECT total_jam FROM penugasan WHERE nomor_proyek = 1);
   ```

   ![](https://data.sinaungoding.com/10/images/image036.png)

3. Setelah berhasil mengeksekusi SQL tersebut, lanjutkan ke Praktikum - Bagian 4.

### Praktikum - Bagian 4: Percobaan FUNGSI AGREGASI <a id="praktikum---bagian-4-percobaan-fungsi-agregasi"></a>

1. Untuk menghitung rata-rata, digunakan tambahan statement AVG. Eksekusi SQL berikut untuk menampilkan rata-rata gaji sesuai kolom gaji dari tabel karyawan.

   `SELECT AVG(gaji) FROM karyawan;`

   ![](https://data.sinaungoding.com/10/images/image037.png)

2. Untuk menghitung nilai tertinggi, digunakan tambahan statement MAX. Eksekusi SQL berikut untuk menampilkan gaji tertinggi sesuai kolom gaji dari tabel karyawan.

   `SELECT MAX(gaji) FROM karyawan;`

   ![](https://data.sinaungoding.com/10/images/image038.png)

3. Untuk menghitung nilai terendah, digunakan tambahan statement MIN. Eksekusi SQL berikut untuk menampilkan gaji terendah sesuai kolom gaji dari tabel karyawan.

   `SELECT MIN(gaji) FROM karyawan;`

   ![](https://data.sinaungoding.com/10/images/image039.png)

4. Untuk menghitung total gaji keseluruhan digunakan tambahan statement SUM. Eksekusi SQL berikut untuk menampilkan total gaji sesuai kolom gaji dari tabel karyawan.

   `SELECT SUM(gaji) FROM karyawan`

   ![](https://data.sinaungoding.com/10/images/image040.png)

5. Untuk menunjukkan jumlah baris pada kolom yang diinginkan digunakan COUNT\(\). Eksekusi SQL berikut untuk menampilkan jumlah baris pada kolom dari tabel karyawan.

   `SELECT COUNT(gaji) FROM karyawan;`

   ![](https://data.sinaungoding.com/10/images/image041.png)

