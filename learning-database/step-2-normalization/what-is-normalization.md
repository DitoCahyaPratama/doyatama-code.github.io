# What is Normalization ?

## Pengertian normalisasi

Normalisasi diartikan sebagai suatu teknik yang menstrukturkan/ mendekomposisi/ memecah data dalam cara–cara tertentu untuk mencegah timbulnya permasalahan pengolahan data dalam basis data. Permasalahan yang dimaksud adalah berkaitan dengan penyimpangan–penyimpangan \(anomalies\) yang terjadi akibat adanya kerangkapan data dalam relasi dan inefisiensi pengolahan. Proses normalisasi akan menghasilkan relasi yang optimal, yaitu :

1. Memiliki struktur record yang mudah untuk dimengerti.
2. Memiliki struktur record yang sederhana dalam pemeliharaan.
3. Memiliki struktur record yang mudah untuk ditampilkan kembali untuk memenuhi kebutuhan pemakai.
4. Minimalisasi kerangkapan data guna meningkatkan kinerja sistem.

Dalam pendekatan normalisasi, perancangan basis data bertitik tolak dari situasi nyata. Ia telah memiliki item–item data yang siap ditempatkan dalam baris dan kolom pada tabel–tabel relasional. Demikian juga dengan sejumlah aturan tentang keterhubungan antara item–item data tersebut. Sementara pendekatan model data ER lebih tepat dilakukan jika yang diketahui baru prinsip sistem secara keseluruhan.

## Atribut Tabel

Atribut identik dengan pemakaian istilah kolom data. Istilah atribut ini lebih umum digunakan dalam perancangan basis data, karena istilah itu lebih impresif dalam menunjukkan fungsinya sebagai pembentuk karakteristik \(sifat–sifat\) yang melekat pada sebuah table.

1. **Atribut Sederhana \(Simple Attribute\) dan Atribut Komposit \(Composite Attribute\)**

   Atribut sederhana adalah atribut atomik yang tidak dapat dipilah lagi. Sementara atribut komposit merupakan atribut yang masih dapat diuraikan lagi menjadi sub–sub atribut yang masing–masing memiliki makna.

2. **Atribut Bernilai Tunggal \(Single Valued Attribute\) dan Atribut Bernilai Banyak \(Multi Valued Atrtribute\)**

   Atribut bernilai tunggal ditujukan pada atribut–atribut yang memiliki paling banyak satu nilai untuk setiap basis data. Pada data mahasiswa, semua atribut \(nim, nama\_mhs, alamat\_mhs dan tgl\_lahir\) merupakan atribut bernilai tunggal, karena atribut–atribut tersebut hanya dapat berisi 1 \(satu\) nilai. Jika seorang mahasiswa yang memiliki 2 \(dua\) tempat tinggal, maka hanya salah satu saja yang boleh diisikan ke dalam atribut alamat\_mhs.

3. **Atribut Harus Bernilai \(Mandatory Attribute\) dan Nilai Null**

   Ada sejumlah atribut pada sebuah tabel yang kita tetapkan harus berisi data. Jadi nilainya tidak boleh kosong. Atribut semacam ini disebut Mandatory Attribute. Pada tabel mahasiswa, misalnya atribut nim dan nama\_mhs dapat kita golongkan sebagai Mandatory Attribute, karena setiap mahasiswa yang datanya ingin disimpan ke tabel tersebut, paling tidak harus diketahui dengan pasti nim dan namanya. Sebaliknya ada atribut–atribut lain dari suatu tabel yang nilainya boleh dikosongkan \(Non Mandatory Attribute\). Nilai Null digunakan untuk menyatakan/ mengisi atribut–atribut demikian yang nilainya memang belum siap atau tidak ada.

4. **Atribut Turunan**

   Atribut turunan adalah atribut yang nilai–nilainya diperbolehkan dari pengolahan atau dapat diturunkan dari atribut atau tabel lain yang berhubungan. Atribut demikian sebetulnya dapat ditiadakan dari sebuah tabel, karena nilai–nilainya bergantung pada nilai yang ada di atribut lainnya. Penambahan atribut angkatan dan IP \(Indeks Prestasi\) pada tabel mahasiswa merupakan contoh atribut turunan

## Domain dan Tipe Data

* Penetapan tipe data pada setiap atribut \(kolom\) digunakan untuk keperluan penentuan struktur setiap tabel. Penetapan tipe data ini akan berimplikasi pada adanya batas–batas nilai yang mungkin disimpan/diisikan ke setiap atribut tersebut. Jika kita menetapkan bahwa tipe data untuk sebuah atribut adalah integer, maka kita hanya mungkin untuk menyimpan data angka yang bulat diantara –32.768 hingga 32.768. Kita tidak mungkin untuk memasukkan data di luar batas nilai tersebut, data pecahan apalagi data berupa string/text.
* Domain memiliki banyak kesamaan pengertian dengan fungsi tipe data tersebut. Akan tetapi, tipe data merujuk pada kemampuan penyimpanan data yang mungkin bagi suatu atribut secara fisik, tanpa melihat layak tidaknya data tersebut bila dilihat dari kenyataan pemakaiannya. Sementara domain nilai lebih ditetapkan pada batas–batas nilai yang diperbolehkan bagi suatu atribut, dilihat dari kenyataanya yang ada.
* Contoh : pada tabel kuliah, ditetapkan tipe data untuk atribut sks adalah integer. Dengan begitu secara fisik kita dapat menyimpan nilai –1, 0 atau 100 untuk atribut sks. Tetapi kita mengetahui dengan pasti, bahwa nilai–nilai tersebut tidak pantas \(invalid\) untuk menjadi data pada atribut sks. Lalu nilai–nilai yang boleh \(valid\) untuk atribut sks adalah 1, 2, 3, 4 dan 6, maka dapat dikatakan, domain nilai untuk atribut sks adalah 1, 2, 3, 4 dan 6.

## Ketergantungan Fungsional \(Fungsional Dependency\)

Diberikan sebuah tabel T berisi paling sedikit 2 buah atribut, yaitu A dan B. Kita dapat menyatakan notasi berikut ini:

A → B

Yang berarti A secara fungsional menentukan B atau B secara fungsional tergantung pada A, jika dan hanya jika setiap kumpulan baris \(row\) yang ada di tabel T, pasti ada 2 baris data \(row\) di tabel dengan nilai A yang sama, maka nilai B pasti juga sama. Definisi yang paling formal untuk itu adalah : Diberikan 2 row r1 dan r2 dalam tabel T dimana A → B. jika `r1(A) = r2(A) maka r1(B) = r2(B)`

![](https://data.sinaungoding.com/06/images/01.png)

Dengan melihat data di atas dan dengan pertimbangan intuisi kita, maka ketergantungan fungsional yang dapat kita ajukan adalah:

* nim → nama\_mhs

  yang berarti bahwa atribut nama\_mhs hanya tergantung pada atribut nim. Hal ini dibuktikan dari fakta : untuk setiap nilai nim yang sama maka pasti nilai nama\_mhsnya juga sama.

* nama\_kul, nim → indeks\_nilai

  yang berarti bahwa atribut indeks\_nilai tergantung pada atribut nama\_kul dan nim secara bersama–sama, memang kita tidak dapat menunjukkan fakta, bahwa untuk setiap nilai nama\_kul dan nim yang sama, maka nilai indeks\_nilainya juga sama, karena nama\_kul, nim merupakan key \(sehingga bersifat unik\) untuk tabel tersebut. Tetapi, ketergantungan fungsional tersebut sesuai dengan pengertian bahwa setiap indeks\_nilai diperuntukkan pada mahasiswa tertentu untuk mata kuliah tertentu yang diambilnya.

Tanpa memperhatikan pengertian ketergantungan secara alamiah terhadap tabel tersebut, kita juga dapat mengajukan sejumlah ketidaktergantungan \(non KF\) dengan hanya melihat fakta yang ada,yaitu :

* nama\_kul ↛ nim

  yang artinya atribut nim tidak tergantung pada atribut nama\_kul. Buktinya terlihat pada row 1 dan row 2 : dengan nilai nama\_kul yang sama, tapi nilai nimnya berbeda.

* nim ↛ nideks\_nilai

  yang artinya atribut indeks\_nilai tidak bergantung pada atribut nim. Buktinya terlihat pada row 1 dan row 3 : dengan nilai nim yang sama, tapi nilai indeks\_nilai berbeda.

## Normalisasi dan Ketergantungan Fungsional

Dalam perspektif normalisasi, sebuah basis data dapat dikatakan baik, jika setiap tabel yang menjadi unsur pembentuk basis data tersebut juga telah berada dalam keadaan baik atau normal. Selanjutnya, sebuah tabel dapat dikategorikan baik \(efisien\) atau normal, jika telah memenuhi 3 \(tiga\) kriteria berikut :

1. Jika ada dekomposisi \(penguraian\) tabel, maka dekomposisinya harus dijamin aman \(Lossless–Join Decomposition\).
2. Terpeliharanya ketergantungan fungsional pada saat perubahan data \(Dependency Preservation\).
3. Tidak melanggar `Boyce–Code Normal Form (BCNF)`

## Lossless–Join Decomposition

Dekomposisi memang merupakan upaya untuk mendapatkan tabel yang baik. Tetapi jika tidak hati–hati, upaya ini justru dapat menghasilkan kesalahan. Dekomposisi yang benar terjadi jika tabel–tabel hasil dekomposisi kita gabungkan kembali dapat menghasilkan tabel awal sebelum didekomposisi. Dekomposisi yang benar semacam ini disebut Lossless–Join Decomposition atau Lossless Decomposition \(dekomposisi aman\).

Di bawah ini contoh abstrak yang menghasilkan dekomposisi tidak aman \(Lossy–Join Decomposition\) : Diasumsikan ada table XYZ yang didefinisikan dua buah ketergantungan fungsional X → Y dan Y → Z. Kedua ketergantungan fungsional tersebut diperoleh dari pengamatan terhadap data yang kurang memadai atau karena asumsi yang kurang tepat.

## Dependency Preservation

Dependency Preservation \(pemeliharaan ketergantungan\) merupakan kriteria kedua yang harus dapat dicapai untuk mendapatkan tabel dan basis data yang baik. Ketika kita melakukan perubahan data, maka harus bisa dijamin agar perubahan tersebut tidak menghasilkan inkonsistensi data yang mengakibatkan ketergantungan fungsional yang sudah benar menjadi tidak terpenuhi. Akan tetapi, dalam upaya untuk memelihara ketergantungan fungsional yang ada untuk tetap terpenuhi tersebut, prosesnya harus dapat dilakukan dengan efisien.

Bentuk–Bentuk Normalisasi Normalisasi data adalah proses yang berkaitan dengan model data relasional untuk mengorganisasi himpunan data dengan ketergantungan dan keterkaitan yang tinggi/ erat. Hasil dari proses normalisasi adalah tabel–tabel data dalam bentuk normal \(normal form\), yaitu tabel–tabel data yang terhindar dari :

* Pengulangan informasi.
* Potensi inkonsistensi data pada operasi pengubahan.

