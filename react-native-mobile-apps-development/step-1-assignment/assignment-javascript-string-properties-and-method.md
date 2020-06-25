---
description: >-
  Sebelum kalian mengerjakan assignment alangkah baiknya kalian untuk
  mempelajari tentang Properties & Method
---

# Assignment - JavaScript String Properties & Method

Tapi...... jika kalian sudah mempelajarinya yukk .. kalian bisa langsung check assignment nya .... Selamat Mengerjakan :\)

## **Question No. 1 \(Membuat kalimat\)**

Terdapat kumpulan variable dengan data string sebagai berikut

```text
var word = 'JavaScript'; 
var second = 'is'; 
var third = 'awesome'; 
var fourth = 'and'; 
var fifth = 'I'; 
var sixth = 'love'; 
var seventh = 'it!';
```

Buatlah agar kata-kata di atas menjadi satu kalimat . Output:

```text
JavaScript is awesome and I love it! 
```

## **Question No.2 Mengurai kalimat \(Akses karakter dalam string\)**

Terdapat satu kalimat seperti berikut:

```text
var sentence = "I am going to be React Native Developer"; 

var exampleFirstWord = sentence[0] ; 
var exampleSecondWord = sentence[2] + sentence[3]  ; 
var thirdWord; // lakukan sendiri 
var fourthWord; // lakukan sendiri 
var fifthWord; // lakukan sendiri 
var sixthWord; // lakukan sendiri 
var seventhWord; // lakukan sendiri 
var eighthWord; // lakukan sendiri 

console.log('First Word: ' + exampleFirstWord); 
console.log('Second Word: ' + secondWord); 
console.log('Third Word: ' + thirdWord); 
console.log('Fourth Word: ' + fourthWord); 
console.log('Fifth Word: ' + fifthWord); 
console.log('Sixth Word: ' + sixthWord); 
console.log('Seventh Word: ' + seventhWord); 
console.log('Eighth Word: ' + eighthWord)
```

Buat menjadi Output berikut:

```text
First word: I 
Second word: am 
Third word: going 
Fourth word: to 
Fifth word: be 
Sixth word: React 
Seventh word: Native 
Eighth word: Developer
```

## **Question No. 3 Mengurai Kalimat \(Substring\)**

```text
var sentence2 = 'wow JavaScript is so cool'; 

var exampleFirstWord2 = sentence2.substring(0, 3); 
var secondWord2; // do your own! 
var thirdWord2; // do your own! 
var fourthWord2; // do your own! 
var fifthWord2; // do your own! 

console.log('First Word: ' + exampleFirstWord2); 
console.log('Second Word: ' + secondWord2); 
console.log('Third Word: ' + thirdWord2); 
console.log('Fourth Word: ' + fourthWord2); 
console.log('Fifth Word: ' + fifthWord2);
```

Uraikan lah kalimat `sentence2` di atas menjadi kata-kata penyusunnya. Output:

```text
First Word: wow 
Second Word: JavaScript 
Third Word: is 
Fourth Word: so 
Fifth Word: cool 
```

## **Question No. 4 Mengurai Kalimat dan Menentukan Panjang String**

```text
var sentence3 = 'wow JavaScript is so cool'; 

var exampleFirstWord3 = sentence3.substring(0, 3); 
var secondWord3; // do your own! 
var thirdWord3; // do your own! 
var fourthWord3; // do your own! 
var fifthWord3; // do your own! 

var firstWordLength = exampleFirstWord3.length  
// lanjutkan buat variable lagi di bawah ini 
console.log('First Word: ' + exampleFirstWord3 + ', with length: ' + firstWordLength); 
console.log('Second Word: ' + secondWord3); 
console.log('Third Word: ' + thirdWord3); 
console.log('Fourth Word: ' + fourthWord3); 
console.log('Fifth Word: ' + fifthWord3); 
```

Output:

```text
First Word: wow, with length: 3 
Second Word: JavaScript, with length: 10 
Third Word: is, with length: 2 
Fourth Word: so, with length: 2 
Fifth Word: cool, with length: 4
```

## Tugas Conditional

* If-else

Petunjuk : Kita akan memasuki dunia game werewolf. Pada saat akan bermain kamu diminta memasukkan nama dan peran . Untuk memulai game pemain harus memasukkan variable `nama` dan `peran`. Jika pemain tidak memasukkan nama maka game akan mengeluarkan warning “`Nama harus diisi!`“. Jika pemain memasukkan nama tapi tidak memasukkan peran maka game akan mengeluarkan warning “`Pilih Peranmu untuk memulai game`“. Terdapat tiga peran yaitu penyihir, guard, dan werewolf. Tugas kamu adalah membuat program untuk mengecek input dari pemain dan hasil response dari game sesuai input yang dikirimkan.

> Petunjuk:
>
> * Nama dan peran diisi manual dan bisa diisi apa saja
> * Nama tidak perlu dicek persis sesuai dengan input/output
> * Buat kondisi if-else untuk masing-masing peran

Input:

```text
var nama = "John"
var peran = ""
```

Output:

```text
// Output untuk Input nama = '' dan peran = ''
"Nama harus diisi!"
 
//Output untuk Input nama = 'John' dan peran = ''
"Halo John, Pilih peranmu untuk memulai game!"
 
//Output untuk Input nama = 'Jane' dan peran 'Penyihir'
"Selamat datang di Dunia Werewolf, Jane"
"Halo Penyihir Jane, kamu dapat melihat siapa yang menjadi werewolf!"
 
//Output untuk Input nama = 'Jenita' dan peran 'Guard'
"Selamat datang di Dunia Werewolf, Jenita"
"Halo Guard Jenita, kamu akan membantu melindungi temanmu dari serangan werewolf."
 
//Output untuk Input nama = 'Junaedi' dan peran 'Werewolf'
"Selamat datang di Dunia Werewolf, Junaedi"
"Halo Werewolf Junaedi, Kamu akan memakan mangsa setiap malam!" 
```

* Switch Case

Kamu akan diberikan sebuah tanggal dalam tiga variabel, yaitu `hari`, `bulan`, dan `tahun`. Disini kamu diminta untuk membuat format tanggal. Misal tanggal yang diberikan adalah hari 1, bulan 5, dan tahun 1945. Maka, output yang harus kamu proses adalah menjadi 1 Mei 1945.

Gunakan `switch case` untuk kasus ini!

Contoh:

```text
var hari = 21; 
var bulan = 1; 
var tahun = 1945;
//  Maka hasil yang akan tampil di console adalah: '21 Januari 1945'; 
```

**Skeleton Code / Code yang dicontohkan yang perlu diikuti dan dimodifikasi**

```text
var tanggal; // assign nilai variabel tanggal disini! (dengan angka antara 1 - 31)
var bulan; // assign nilai variabel bulan disini! (dengan angka antara 1 - 12)
var tahun; // assign nilai variabel tahun disini! (dengan angka antara 1900 - 2200)
```

