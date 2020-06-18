---
description: >-
  Sebelum kita membahas mengenai React Native, kita perlu belajar terlebih
  dahulu basic dari CLI atau biasa disebut dengan Command Line.
---

# Command Line

## Apa itu CLI / Command Line Interface

**CLI** adalah singkatan dari **Command Line Interface**.

**CLI** adalah program yang memungkinkan pengguna mengetik perintah teks yang memerintahkan komputer untuk melakukan tugas tertentu.

Meskipun begitu kuat, penggunaan CLI tidak selalu diterima dengan baik. Pemula enggan menggunakannya, berpikir bahwa CLI hanya untuk pengguna tingkat lanjut. Sebenarnya tidak demikian.

Saat ini penerapan CLI \(command line interface\) di komputer personal sudah sangat jarang. Alasannya karena banyak pengguna yang memilih untuk menggunakan GUI \(graphic user interface\) sebagai penghubung ia dengan sistem komputer.

Karena komputer dengan Interface CLI sebenarnya sering digunakan oleh pengguna profesional untuk melakukan tugas komputer tertentu tertentu misalnya untuk mengelola & mengurus server jaringan, hosting web, administrasi, keamanan dan sebagainya. Bahkan CLI merupakan sistem andalan milik hacker

Berikut ini beberapa contohnya :

## Menuju folder / direktori tertentu

Untuk menuju _folder_ atau direktori tertentu bisa gunakan perintah `cd` atau kepanjangan dari _change directory_

```c
// Menuju Desktop
$ cd Desktop
// Menuju ke direktori parent (sebelumnya)
$ cd ..
```

## Mengetahui alamat dari direktori yang sedang dibuka

Terkadang kita butuh tahu sedang dimana posisi terminal kita berjalan. Perintah untuk fungsi ini yaitu `pwd` atau kependekan dari path of working directory

```c
$ pwd
/home/users
// sedang berada di folder home/users
```

## Mengetahui daftar isi dari sebuah direktori/folder

 Anda bisa gunakan perintah `ls` atau `dir` . contohnya sebagai berikut

```c
$ ls 
Document Desktop Image index.html
$ dir
Document Desktop Image index.html 
```

## Membuat folder baru

Perintahnya adalah `mkdir` atau singkatan dari _make directory_. contohnya sebagai berikut

```c
// membuat folder baru bernama new-folder
$ mkdir new-folder
// mengecek apakah sudah berhasil buat folder baru
$ ls
new-folder ... ... 
```

## Membuat file baru

Gunakan perintah `touch` untuk membuat file baru

```c
// membuat file index.html
$ touch index.html
// mengecek apakah sudah berhasil buat file baru
$ ls 
index.html ... ... 
```

## Software terminal / command line yang direkomendasikan

Untuk OS Windows, _terminal_ bawaannya adalah _command prompt_ atau cmd yang relatif kurang nyaman untuk dipakai dalam tahap _development_. Oleh karena itu direkomendasikan untuk _install terminal_ di bawah ini agar lebih optimal dalam mengerjakan _project_.

* Cmder, _link download_: [cmder](https://cmder.net/)
* Git bash, Git bash biasanya ter-_install_ jika kita meng-_install_ git di pc/laptop kita.

