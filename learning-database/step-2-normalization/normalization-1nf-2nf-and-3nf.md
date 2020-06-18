# Normalization 1NF, 2NF And 3NF

## Bentuk Normal Tahap Pertama \(1st Normal Form\)

Suatu tabel memenuhi 1stNF jika dan hanya jika tabel tersebut tidak memiliki atribut bernilai banyak atau lebih dari satu atribut dengan domain nilai yang sama.

## Bentuk Normal Tahap Kedua \(2nd Normal Form\)

Suatu tabel memenuhi 2ndNF jika dan hanya jika :

1. Tabel tersebut memenuhi 1stNF
2. Setiap atribut yang bukan kunci utama \(primary key\) tergantung secara fungsional terhadap semua atribut kunci utama dan bukan tergantung secara fungsional hanya pada sebagian atribut kunci utama.

## Bentuk Normal Tahap Ketiga \(3rd Normal Form\)

Suatu tabel memenuhi bentuk normal 3rdNF jika dan hanya jika :

1. Tabel tersebut memenuhi 2ndNF.
2. Tidak ada atribut bukan kunci tergantung secara transitive pada kunci utama.

## Langkah-langkah prakikum

### **Langkah 1**

1. Bukalah berkas spreadsheet bernama `DataSoftwareHouseAustria.XLSX` di [sini](https://data.sinaungoding.com/06/files/DataSoftwareHouseAustria.xlsx) yang dilampirkan bersama jobsheet ini.
2. File tersebut berisi data pegawai software house di Austria beserta atribut lain yang mendukung project yang dikerjakan di perusahaan tersebut.
3. Teliti setiap atribut yang tertulis pada data tersebut dan amati ketidak sesuaian atribut yang ada sehingga mempersulit proses insert, update, delete dan modifikasi.
4. Pertimbangkan pula bagaimana bentuk yang baik dan sesuai dengan aturan normalisasi yang efisien.

![](https://data.sinaungoding.com/06/images/02.png)

### **Langkah 2**

* Normalisasi data sesuai bentuk normal kesatu karena data pada langkah 1 tidak memenuhi bentuk normal data bagian satu \(1NF\). Maka akan menghasilkan dekomposisi tabel sebagai berikut :

![](https://data.sinaungoding.com/06/images/04.png)

![](https://data.sinaungoding.com/06/images/03.png)

* Lakukan pengecekan \(Lossless–Join Decomposition\) pada tabel baru hasil dekomposisi tersebut! \

### **Langkah 3**

1. Pengecekan FD pada tabel hasil langkah 2 akan menghasilkan data FD sebagai berikut :

   Pada tabel project

   num\_project → name\_project

   Pada tabel employee

   * {num\_project, num\_employee, num\_jobclass} ↛ name\_employee
   * {num\_project, num\_employee, num\_jobclass} ↛ street\_address
   * {num\_project, num\_employee, num\_jobclass} ↛ city
   * {num\_project, num\_employee, num\_jobclass} ↛ postal\_code
   * {num\_project, num\_employee, num\_jobclass} ↛ name\_jobclass
   * {num\_project, num\_employee, num\_jobclass} ↛ chr\_per\_hour
   * {num\_project, num\_employee, num\_jobclass} ↛ hours\_billed

     **FD**

   * num\_project → name\_project
   * no\_employee →{name\_employee, street\_address, city, postal\_code}
   * no\_jobclass →{name\_jobclass, chr\_per\_hours}
   * {num\_project, num\_employee,num\_jobclass} → hours\_billed

2. Normalisasi tabel menjadi bentuk 2NF. Berdasarkan informasi FD maka dekomposisi tabel yang semula 2 tabel menjadi 4 tabel sebagai berikut :
   * project{num\_project, name\_project}
   * employee{no\_employee, name\_employee, street\_address, city, postal\_code}
   * jobclass{no\_jobclass, name\_jobclass, chr\_per\_hours}
   * hours{num\_project, num\_employee,num\_jobclass, hours\_billed}
3. Lakukan pengecekan `(Lossless–Join Decomposition)` dan `(dependency preservation)` pada tabel baru hasil dekomposisi tersebut! \

### **Langkah 4**

1. Mencari hubungan syarat 3NF dengan mempertimbangkan X → A sesuai dengan ketentuan 3NF Terdapat beberapa non key yang memiliki ketergantungan dengan non key lain, sesuai FD baru sebagai berikut:
   * {city, street\_address} → postal\_code dimana X adalah superkey
   * name\_project → {name\_employee, name\_jobclass} dimana X adalah superkey
   * {name\_employee, name\_jobclass} → chr\_per\_hours dimana dimana X adalah superkey
2. Berdasarkan FD tersebut maka tabel pada langkah 3 diperbaharui dekomposisinya menjadi :
   * project{num\_project, name\_project}
   * employee{no\_employee, name\_employee, street\_address }
   * jobclass{no\_jobclass, name\_jobclass, chr\_per\_hours}
   * hours{num\_project, num\_employee,num\_jobclass, hours\_billed}
   * **address{city, street\_address, postal\_code**}
   * **jobclass\_detail{name\_project, name\_employee, name\_jobclass}**
   * **charge{name\_employee, name\_jobclass, chr\_per\_hours}**
3. Lakukan pengecekan `(Lossless–Join Decomposition)` dan `(dependency preservation)` pada tabel baru hasil dekomposisi tersebut! \

