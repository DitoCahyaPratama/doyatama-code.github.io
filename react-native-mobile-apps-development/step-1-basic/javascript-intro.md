---
description: >-
  Pada materi sebelumnya, kita sudah belajar mengenai CLI dan Git. Dan pada kali
  ini, kita akan fokus mempelajari konsep Javascript
---

# Javascript – Intro

Javascript merupakan salah satu bahasa pemrograman yang terpopuler di dunia. Javascript membuat aplikasi web menjadi interaktif tanpa reload halaman. Hampir semua browser modern yang kita ketahui dapat menjalankan javascript agar website yang ditampilkan lebih menarik.

## Menjalankan Javascript 

Ada bermacam cara untuk menjalankan kode javascript yang kita buat, di antaranya:

1. Menjalankan javascript di console browser
2. Menjalankan javascript di tools online seperti [repl.it](https://repl.it/repls)
3. Menjalankan javascript dengan nodejs

Pada materi ini kita akan mencoba untuk menjalankan script dengan nodejs.

Nodejs adalah software berbasis pemrograman javascript yang dijalankan di sisi server. Jika biasanya javascript kita kenal erat kaitannya dengan client/browser tapi dengan nodejs ini kita bisa membangun server menggunakan bahasa javascript.

## Install Nodejs

Pertama-tama tentu kita harus menginstall terlebih dahulu nodejs di komputer kita. Berikut ini link untuk download [nodejs](https://nodejs.org/en/download/) \(disarankan memilih versi LTS\). Untuk OS Windows dan macOs tinggal diikuti saja instalasinya sampai selesai, sedangkan untuk Ubuntu 18.04 kamu bisa install mengikuti [tutorial dari digitalocean](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04).

Untuk mengecek apakah instalasi nodejs sudah berhasil kita bisa jalankan script di terminal kita:

```text
$ node -v 
v10.16.1
$ npm -v 
6.9.0
```

dengan perintah tersebut, diketahui saat ini terinstall node dengan versi 10 dan npm versi 6.

## Hello world 

Untuk menjalankan javascript dengan nodejs mari kita coba dengan menuliskan script di sebuah file index.js .

Buatlah file dengan nama index.js kemudian tulis code di dalam file tersebut seperti berikut:

```text
var sayHello = "Hello World!" 
console.log(sayHello)
```

kemudian simpan file tersebut \(save\). Setelah itu kita bisa menjalankan script pada index.js tersebut dengan memberikan perintah seperti berikut pada terminal:

```text
$ node index.js
```

secara otomatis pada terminal kita akan muncul “`Hello World!`” . \(Selamat Anda telah berhasil menjalankan program pertama Anda 😁\)

Demikian cara untuk menjalankan Javascript dengan nodejs.

## Data Type 

Data Type atau dalam bahasa indonesia Tipe Data adalah sekumpulan informasi yang memiliki nilai dan karakteristik tertentu. Beberapa contoh tipe data pada javascript di antaranya:

1. **Number** : tipe data angka
2. **String** : tipe data berupa text atau kumpulan karakter, biasanya string dibungkus dalam tanda petik ganda \(double quote\) atau tanda petik tunggal \(single quote\).
3. **Boolean:** tipe data dengan nilai `true` atau `false`

## Variable

Variable adalah suatu blok data untuk menampung sekumpulan data dengan berbagai tipe data apapun. Dengan variable kita bisa menyimpan suatu nilai untuk kemudian kita olah kembali pada program kita. Untuk deklarasi variable dalam javascript kita bisa gunakan sintaks `var` lalu diikuti nama variablenya.

```text
var name = "John" // Tipe
var angka = 12
var todayIsFriday = false 

console.log(name) // "John"
console.log(angka) // 12
console.log(todayIsFriday) // false
```

Waspadai pendeklarasian variable yang tidak bernilai !

```text
var items
console.log(items) // Undefined
```

## Operator <a id="operator"></a>

Operator adalah karakter khusus yang merepresentasikan sebuah tindakan. Operator terbagi ke dalam beberapa jenis:

1. Operator Aritmatika Operator yang melibatkan operasi matematika seperti tambah, kurang, kali, bagi.
   * Tambah **\(+\)**
   * Kurang \(**–**\)
   * Kali \(**\***\)
   * Bagi \(**/**\)
   * Modulus \(**%**\) Modulus adalah sisa bagi. Contohnya 5%3 hasilnya adalah 2, 100%5 hasilnya 0.
2. Operator Assignment \(`=`\), Operator untuk mendaftarkan atau meng-assign suatu nilai ke dalam suatu variable  


   ```text
   var angka 
   angka = 10 // Contoh assignment variable angka dengan nilai 10
   ```

3. Operator Perbandingan, Operator yang membandingkan suatu nilai dengan nilai yang lain. Hasil dari perbandingan ini akan dikembalikan dalam tipe data boolean `true` atau `false`.
   * Equal Operator \(`==`\)  


     ```text
     var angka = 100
     console.log(angka == 100) // true
     console.log(angka == 20) // false
     ```

   * Not Equal \( `!=` \)  


     ```text
     var sifat = "rajin"
     console.log(sifat != "malas") // true
     console.log(sifat != "bandel") //true 
     ```

   * Strict Equal \( `===` \) Selain membandingkan dua nilai nya, strict equal juga membandingkan tipe datanya apakah sama atau tidak  


     ```text
     var angka = 8
     console.log(angka == "8") // true, padahal "8" adalah string.
     console.log(angka === "8") // false, karena tipe data nya berbeda
     console.log(angka === 8) // true 
     ```

   * Strict not Equal \( `!==` \) Kebalikan dari strict equal.  


     ```text
     var angka = 11
     console.log(angka != "11") // false, padahal "11" adalah string
     console.log(angka !== "11") // true, karena tipe datanya berbeda
     console.log(angka !== 11) // false
     ```

   * Kurang dari & Lebih Dari \( `<`, `>`, `<=`, `>=`\)  


     ```text
     var number = 17
     console.log( number < 20 ) // true
     console.log( number > 17 ) // false
     console.log( number >= 17 ) // true, karena terdapat sama dengan
     console.log( number <= 20 ) // true
     ```
4. Operator Kondisional, Operator yang mengkombinasikan dua nilai kebenaran . Terdapat operator AND \(`&&`\) dan OR \(`||`\)
   * OR \( `||` \)  


     ```text
     console.log(true || true); // true
     console.log(true || false); // true
     console.log(true || false || false); // true
     console.log(false || false); // false
     ```

   * AND \( `&&` \)  


     ```text
     console.log(true && true); // true
     console.log(true && false); // false
     console.log(false && false); // false
     console.log(false && true && true); // false
     console.log(true && true && true); // true
     ```

