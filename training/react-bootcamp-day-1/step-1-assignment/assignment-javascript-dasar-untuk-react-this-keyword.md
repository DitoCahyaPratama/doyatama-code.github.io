---
description: >-
  Sebelum kalian mengerjakan assignment alangkah baiknya kalian untuk
  mempelajari apa itu javascipt dasar untuk react tentang "this" keyword.
---

# Assignment - JavaScript Dasar untuk React - "this" keyword

Tapi...... jika kalian sudah mempelajarinya yukk .. kalian bisa langsung check assignment nya .... Selamat Mengerjakan :\)

## **Question 1**

Jelaskan istilah dari _this_ di JavaScript!

## **Question 2**

Ubahlah beberapa _function_ dibawah ini ke bentuk _arrow function_

```text
function getNamaLengkap(namaDepan, namaBelakang) {
   return `${namaDepan} ${namaBelakang}`;
}
 
function getNamaDepan(namaLengkap) {
   return namaLengkap.split(' ')[0];
}
 
function consoleHai() {
   console.log('hai');
}
```

## **Question 3**

Di bawah ini, jika kita memanggil fungsi getName yang ada di object sebuahObject, maka kita berhasil mendapatkan outputnya. Namun, jika kita memanggil fungsi getName yang ada di object sebuahObjectLain, maka kita akan mendapatkan output undefined. Apa yang salah dari object sebuahObjectLain ? dan bagaimana cara memperbaikinya ? Jelaskan!

```text
const sebuahObject = {
   name: 'Bejo Jhonson',
   getName() {
       return this.name;
   }
}
 
const sebuahObjectLain = {
   name: 'Bejo Jhonson',
   getName: () => this.name
}
```

**Soal 4**

Dapatkah code dibawah ini berjalan dengan benar ? Jelaskan apa yang terjadi!

```text
const profil = {
   namaDepan: 'Bejo',
   namaBelakang: 'Jhonson',
   getName() {
       this.name = `${this.namaDepan} ${this.namaBelakang}`;
       return this.name;
   }
}

profil.getName();
```

