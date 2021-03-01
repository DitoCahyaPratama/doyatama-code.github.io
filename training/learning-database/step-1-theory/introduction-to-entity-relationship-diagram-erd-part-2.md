# Introduction to Entity Relationship Diagram \(ERD\) Part 2

## Pendahuluan

### Pemodelan Data

Definisi singkat \(dalam lingkup software engineering\) untuk pemodelan data adalah proses pembuatan model data \(data model\) untuk sebuah sistem informasi yang melibatkan teknik-teknik formal tertentu. Dalam definisi yang lebih lengkap, data modelling berarti sebuah proses penganalisisan persyaratan- persyaratan data \(data requirements\) yang dibutuhkan untuk mendukung terlaksananya proses-proses bisnis \(business processes\) dalam lingkup sistem informasi pada suatu organisasi.

Tujuan utama dari data modelling adalah mengubah persyaratan-persyaratan data pengguna menjadi basisdata yang sesungguhnya \(actual database\) yang memenuhi persyaratan-persyaratan tersebut. Shingga data modelling perlu dilakukan untuk memastikan sistem informasi yang dihasilkan nantinya dapat berfungsi secara benar dan tepat, sesuai dengan persyaratan organisasi yang menggunakannya.

### Data Model

Hasil dari pemodelan data adalah model data \(data model\). Data model adalah sebuah model \(yang berarti perumpamaan atau analogi\) abstrak yang mewakili dan menjelaskan hubungan antara elemen-elemen data pada suatu entitas \(objek\) di dunia nyata.

Contohnya, apabila kita menjumpai data dunia nyata seperti berikut: "sebuah mobil berwarna putih buatan tahun 2017, dimiliki oleh seorang dosen bernama Muhammad Ali." Maka kita dapat membuat sebuah model yang merepresentasikan sifat-sifat mobil dan pemilik berikut hubungan atara keduanya:

![Contoh](https://data.sinaungoding.com/03/images/03-01.png)

Tampilan/bentuk model yang dihasilkan dapat berupa apa saja, namun dalam membuat suatu model kita harus meyakinkan bahwa karakteristik utama dari model semuanya telah ada. Karakteristik utamanya adalah, sebuah model harus dapat menggambarkan dan mewakili jumlah/nilai data yang dimiliki oleh entitasnya berikut hubungan antara masing-masing entitas yang terlibat

Berdasarkan urut-urutan/fase pengembangan dari requirements menuju actual database, data model terbagi menjadi 3 garis besar:

1. Conseptual Data Model \(CDM\)

   Berisi gambaran umum data-data yang harus disimpan berikut signifikansinya pada proses bisnis suatu organisasi. Sifat dari model ini relatif sederhana, idak melibatkan istilah teknis, dan bisa dimengerti oleh semua level manajemen dari lingkungan IT maupun non-IT. Salah satu diagram yang dapat digunakan untuk merepresentasikan model ini adalah Data Structure Diagram \(DSD\).

2. Logical Data Model \(LDM\)

   Berisi gambaran lebih detail mengenai entitas-entitas yang terlibat, atribut, dan hubungan antara satu dengan yang lainnya. Model ini melibatkan entitas, atribut, dan relationship, serta mulai menggunakan istilah-istilah teknis yang berhubungan denga proses bisnis organisasinya. 1 CDM dapat membutuhkan 1 atau lebih LDM. Untuk menggambarkan model ini kita dapat menggunakan Entity Relationship Diagram \(ERD\)

3. Physical Data Model \(PDM\)

   Model ini menjelaskan bagaimana data disimpan secara fisik pada database. Model ini bersigat sangat spesifik dan bergantung \(dependent\) pada jenis/merk DBMS yang digunakan. Model ini melibatkan tabel, kolom, primary key, panjang data. Contoh diagram yang digunakan pada model ini adalah EER Diagram pada MySQL

Pada data modelling saat ini terdapat 2 pendekatan yang paling populer yaitu ![Data Modeling](https://data.sinaungoding.com/03/images/03-02.png)

1. Top-Down

   Adalah pendekatan yang bergerak dari umum ke spesifik. Pendekatan ini baik digunakan untuk membuat model data pada sistem yang sama sekali baru. Pada pendekatan ini, pengguna memberikan gambaran umum sistem dan data apa saja yang perlu disimpan. Analis kemudian mendetailkan \(dengan cara mewawancarai dan mengira-ngira\) lebih lanjut tabel-tabel dalam database berikut kolom-kolomnya.

2. Bottom-Up

   Kebalikan dari metode sebelumnya, pada metode ini dilakukan penalaran yang bergerak dari spesifik ke umum. Pendekatan ini memiliki kelebihan jika digunakan untuk membuat model data berdasarkan sistem yang sudah ada sebelumnya. Dalam pendekatan ini pengguna menunjukkan sistem \(dapat berupa sistem manual maupun yang sudah terkomputerisasi\) yang saat ini berjalan. Analis kemudian memeriksa semua dokumen, formulir, struk, laporan, buku kas, dll. yang terlibat dalam sistem tersebut kemudian menyimpulkan database-nya.

#### ERD Versi Martin <a id="erd-versi-martin"></a>

Selain ERD versi Chen, terdapat juga ERD versi martin yang tidak kalah populer. Pada ERD ini terdapat 5 macam relationship yaitu:

![Martin](https://data.sinaungoding.com/03/images/03-03.png)

#### CASE tools untuk membuat ERD <a id="case-tools-untuk-membuat-erd"></a>

Untuk membuat ERD kita dapat memanfaatkan berbagai macam tools. Ada banyak tools yang dapat digunakan untuk membuat ERD dan tidak ada alasan mutlak untuk memilih tools tertentu diatas tools yang lain. Kita bebas menggunakan tools mana saja yang cocok untuk kebutuhan kita. Bahkan sebenarnya tidak ada keharusan untuk menggunakan tools, apabila mencukupi kita dapat membuat ERD pada kertas atau papan tulis.

Pada praktikum kali ini kita akan mencoba menggunakan salah satu tools untuk membuat ERD versi Chen. Tools tersebut bernama TerraEr. Tools tersebut dipilih karena lisensinya open source, ringan, dan mudah digunakan dimana saja selama ada JRE yang telah diinstal.

### Praktikum <a id="praktikum"></a>

1. Copy file [TerraER3.13.jar](https://data.sinaungoding.com/03/TerraER3.13.jar) ke komputer Anda, untuk menjalankannya dalam komputer Anda harus sudah terinstall Java Runtime Environment \(JRE\)
2. double klik file tersebut atau jalankan perintah `java -jar TerraER3.13.jar` sehingga dapat dilihat seperti pada tampilan di bawah ini

![TeraER](https://data.sinaungoding.com/03/images/03-04.png)

1. Untuk membuat ERD pada TerraEr, kita gunakan toolbar yang berada dibagian atas jendela aplikasi. Buat 1 entitas dengan cara Klik 1x pada ikon persegi berwarna hijau lalu klik 1x juga pada canvas\(jendela utama aplikasi\).

![Entity](https://data.sinaungoding.com/03/images/03-05.png)

1. Untuk mengubah nama entitas, klik 2 kali pada simbol entitas. Beri nama entitas baru tersebut dengan nama `karyawan`.

   ![Karyawan](https://data.sinaungoding.com/03/images/03-06.png)

2. Tambahkan entitas lemah \(weak entity\) dengan cara yang sama seperti cara yang dilakukan untuk menambahkan entitas sebelumnya. Klik 2x dan berinama entitas tersebut dengan nama `tanggungan`

   ![Tanggungan](https://data.sinaungoding.com/03/images/03-07.png)

3. Tambahkan identifying relationship dengan cara menambahkan simbol berbentuk belah ketupat dengan garis tepi ganda.

   ![Relasi](https://data.sinaungoding.com/03/images/03-08.png)

4. Beri nama relationship tersebut dengan nama `memiliki`.

   ![Memiliki](https://data.sinaungoding.com/03/images/03-09.png)

5. Untuk menambahkan properties/attributes, kita gunakan simbol-simbol elips pada bagian tengah panel atas.

   ![properties](https://data.sinaungoding.com/03/images/03-10.png)

6. Untuk menghubungkan attribute dengan entitas atau relationship, kita gunakan `Attribute Connection` dengan mengklik 1x ikon bergambar berikut:

   ![attribut](https://data.sinaungoding.com/03/images/03-11.png)

7. Lalu mengklik 1x pada atribut yang diinginkan kemudian di-drag ke entity atau relationship yang menjadi pemilik dari atribut tadi. Tambahkan 1 atribut kunci dan 1 atribut simple. Lalu hubungkan keduanya dengan entitas kuat karyawan yang telah kita buat sebelumnya.

   ![entity](https://data.sinaungoding.com/03/images/03-12.png)

8. Tambahkan 1 partial key atribut dan 1 attribut simple pada weak entity tanggungan dengan cara yang sama seperti sebelumnya.

   ![](https://data.sinaungoding.com/03/images/03-13.png)

9. Untuk menghubungkan entity dengan relationship kita gunakan button-button yang ada di sebelah kanan panel atas. Ada 4 macam garis penghubung:

   * 1, untuk relationship 1 to....
   * N, untuk relationship many to....
   * 1=, total participation untuk entitas lemah dengan relationship 1 to....
   * N=, total participation untuk entitas lemah dengan relationship Many to....

   ![](https://data.sinaungoding.com/03/images/03-14.png)

10. Hubungkan entitas lemah ‘tanggungan’ dengan relationship ‘memiliki’ menggunakan ‘total participation N’. Klik ikon di atas 1x, lalu klik entity ‘tanggungan’ dan drag ke arah relationship ‘memiliki’.

    ![](https://data.sinaungoding.com/03/images/03-15.png)

11. Dengan cara yang sama, klik penghubung biasa relationship ‘1 to...’ dan hubungkan entity ‘karyawan’ dengan relationship ‘memiliki’.

    ![](https://data.sinaungoding.com/03/images/03-16.png)

12. Beri nama semua atribut pada entitas-entitas yang ada sehingga menjadi seperti berikut:

    ![](https://data.sinaungoding.com/03/images/03-17.png)

