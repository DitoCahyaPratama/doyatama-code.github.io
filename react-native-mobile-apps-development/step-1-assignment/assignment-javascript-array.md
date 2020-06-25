---
description: >-
  Sebelum kalian mengerjakan assignment alangkah baiknya kalian untuk
  mempelajari apa itu array dalam javascipt
---

# Assignment - JavaScript Array

Tapi...... jika kalian sudah mempelajarinya yukk .. kalian bisa langsung check assignment nya .... Selamat Mengerjakan :\)

## Question No. 1 \(Range\) 

Buatlah sebuah function dengan nama range\(\) yang menerima dua parameter berupa number. Function mengembalikan sebuah array yang berisi angka-angka mulai dari angka parameter pertama hingga angka pada parameter kedua. Jika parameter pertama lebih besar dibandingkan parameter kedua maka angka-angka tersusun secara menurun \(descending\).

struktur fungsinya seperti berikut `range(startNum, finishNum) {}`  
Jika parameter pertama dan kedua tidak diisi maka function akan menghasilkan nilai `-1`

```text
// Code di sini
 
console.log(range(1, 10)) //[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
console.log(range(1)) // -1
console.log(range(11,18)) // [11, 12, 13, 14, 15, 16, 17, 18]
console.log(range(54, 50)) // [54, 53, 52, 51, 50]
console.log(range()) // -1 
```

## Question No. 2 \(Range with Step\)

Pada soal kali ini kamu diminta membuat function rangeWithStep yang mirip dengan function range di soal sebelumnya namun parameternya ditambah dengan parameter ketiga yaitu angka step yang menyatakan selisih atau beda dari setiap angka pada array. Jika parameter pertama lebih besar dibandingkan parameter kedua maka angka-angka tersusun secara menurun \(descending\) dengan step sebesar parameter ketiga.

struktur fungsinya seperti berikut `rangeWithStep(startNum, finishNum, step) {}`

```text
// Code di sini
 
console.log(rangeWithStep(1, 10, 2)) // [1, 3, 5, 7, 9]
console.log(rangeWithStep(11, 23, 3)) // [11, 14, 17, 20, 23]
console.log(rangeWithStep(5, 2, 1)) // [5, 4, 3, 2]
console.log(rangeWithStep(29, 2, 4)) // [29, 25, 21, 17, 13, 9, 5] 
```

## Question No. 3 \(Sum of Range\)

Kali ini kamu akan menjumlahkan sebuah range \(Deret\) yang diperoleh dari function range di soal-soal sebelumnya. Kamu boleh menggunakan function range dan rangeWithStep pada soal sebelumnya untuk menjalankan soal ini.

Buatlah sebuah function dengan nama `sum()` yang menerima tiga parameter yaitu angka awal deret, angka akhir deret, dan beda jarak \(step\). Function akan mengembalikan nilai jumlah \(sum\) dari deret angka. contohnya `sum(1,10,1)` akan menghasilkan nilai 55.

ATURAN: Jika parameter ke-3 tidak diisi maka stepnya adalah 1.

```text
// Code di sini
console.log(sum(1,10)) // 55
console.log(sum(5, 50, 2)) // 621
console.log(sum(15,10)) // 75
console.log(sum(20, 10, 2)) // 90
console.log(sum(1)) // 1
console.log(sum()) // 0 
```

## Question No. 4 \(Array Multidimensi\)

Sering kali data yang diterima dari database adalah array yang multidimensi \(array di dalam array\). Sebagai developer, tugas kita adalah mengolah data tersebut agar dapat menampilkan informasi yang diinginkan.

Buatlah sebuah fungsi dengan nama `dataHandling` dengan sebuah parameter untuk menerima argumen. Argumen yang akan diterima adalah sebuah array yang berisi beberapa array sejumlah **n**. Contoh input dapat dilihat dibawah:

```text
//contoh input
var input = [
                ["0001", "Roman Alamsyah", "Bandar Lampung", "21/05/1989", "Membaca"],
                ["0002", "Dika Sembiring", "Medan", "10/10/1992", "Bermain Gitar"],
                ["0003", "Winona", "Ambon", "25/12/1965", "Memasak"],
                ["0004", "Bintang Senjaya", "Martapura", "6/4/1970", "Berkebun"]
            ] 
```

Tugas kamu adalah mengimplementasikan fungsi `dataHandling()` agar dapat menampilkan data-data pada dari argumen seperti di bawah ini:

```text
Nomor ID:  0001
Nama Lengkap:  Roman Alamsyah
TTL:  Bandar Lampung 21/05/1989
Hobi:  Membaca
 
Nomor ID:  0002
Nama Lengkap:  Dika Sembiring
TTL:  Medan 10/10/1992
Hobi:  Bermain Gitar
 
Nomor ID:  0003
Nama Lengkap:  Winona
TTL:  Ambon 25/12/1965
Hobi:  Memasak
 
Nomor ID:  0004
Nama Lengkap:  Bintang Senjaya
TTL:  Martapura 6/4/1970
Hobi:  Berkebun 
```

## Question No. 5 \(Balik Kata\)

Kamu telah mempelajari beberapa method yang dimiliki oleh String dan Array. String sebetulnya adalah sebuah array karena kita dapat mengakses karakter karakter pada sebuah string layaknya mengakses elemen pada array.

Buatlah sebuah function `balikKata()` yang menerima sebuah parameter berupa string dan mengembalikan kebalikan dari string tersebut.

```text
// Code di sini
 
console.log(balikKata("Kasur Rusak")) // kasuR rusaK
console.log(balikKata("SanberCode")) // edoCrebnaS
console.log(balikKata("Haji Ijah")) // hajI ijaH
console.log(balikKata("racecar")) // racecar
console.log(balikKata("I am Sanbers")) // srebnaS ma I 
```

> Dilarang menggunakan sintaks `.split` , `.join` , `.reverse()` , hanya gunakan looping!

## Question No. 6 \(Metode Array\)

Array pada JavaScript memiliki sekumpulan _built-in function_ yang digunakan untuk mempermudah developer untuk mengolah data di dalamnya. Beberapa fungsi yang sering digunakan antara lain `join`, `split`, `slice`, `splice`, dan `sort`. Kerjakanlah tantangan ini untuk memperkuat pengertian kamu tentang _built-in function_ tersebut.

**Tujuan**

* Mengerti Kegunaan dari _Built-in Function_ yang dimiliki Array
* Mampu Menggunakan _Built-in Function_ yang dimiliki Array

**Petunjuk**

```text
//contoh output
["0001", "Roman Alamsyah", "Bandar Lampung", "21/05/1989", "Membaca"]  
```

* Buatlah sebuah _function_ dengan nama `dataHandling2` yang akan menerima input array seperti di atas.
* Gunakan fungsi `splice` untuk memodifikasi variabel tersebut agar menjadi seperti array dibawah. Lalu `console.log` array yang baru seperti di bawah.

```text
["0001", "Roman Alamsyah Elsharawy", "Provinsi Bandar Lampung", "21/05/1989", "Pria", "SMA Internasional Metro"] 
```

* Berdasarkan elemen yang berisikan tanggal/bulan/tahun \(elemen ke-4\), ambil angka bulan dan `console.log` nama bulan sesuai dengan angka tersebut.
  * Gunakan `split` untuk memisahkan antara tanggal, bulan, dan tahun.
  * Format tanggal pada data adalah **dd-mm-YYYY**
  * Misal angka bulan 01, tuliskan “Januari”
  * Gunakan `switch case` untuk menuliskan bulan di atas.
* Pada array hasil `split` dari tanggal/bulan/tahun, lakukan _sorting_ secara _descending_ dan `console.log` array yang sudah di-sort.
* Masih pada array hasil `split` dari elemen tanggal/bulan/tahun, gabungkan semua elemen menggunakan `join` dan pisahkan dengan karakter strip \(-\) lalu `console.log` hasilnya.
* Nama \(elemen ke-2\), harus dibatasi sebanyak 15 karakter saja. Gunakan `slice` untuk menghapus kelebihan karakter dan `console.log` nama yang sudah di-slice, sebelum di-slice pastikan Nama \(elemen ke-2\) sudah dalam bentuk `String` agar bisa di-slice.

**Test-case**

Untuk memastikan program kamu sudah bekerja dengan benar, gunakan _test-case_ dibawah.

```text
var input = ["0001", "Roman Alamsyah ", "Bandar Lampung", "21/05/1989", "Membaca"];
dataHandling2(input);
 
/**
 * keluaran yang diharapkan (pada console)
 *
 * ["0001", "Roman Alamsyah Elsharawy", "Provinsi Bandar Lampung", "21/05/1989", "Pria", "SMA Internasional Metro"]
 * Mei
 * ["1989", "21", "05"]
 * 21-05-1989
 * Roman Alamsyah
 */ 
```

