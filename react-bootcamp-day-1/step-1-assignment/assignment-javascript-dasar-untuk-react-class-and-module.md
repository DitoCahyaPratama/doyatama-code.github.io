---
description: >-
  Sebelum kalian mengerjakan assignment alangkah baiknya kalian untuk
  mempelajari javascipt dasar untuk react tentang Class & Module
---

# Assignment - JavaScript Dasar untuk React - Class & Module

Tapi...... jika kalian sudah mempelajarinya yukk .. kalian bisa langsung check assignment nya .... Selamat Mengerjakan :\)

## **Question 1**

Ubahlah object-object berikut menjadi class. Dan setelah itu, untuk class Benda, buat object yang instansiasinya dari class Benda, dengan properti object persis dengan halGhaibLain. Dan juga buat class baru yang inherit dengan class Benda, dengan menambahkan property “dasar” dan juga method actionLain yang memunculkan console log “Ini action lain”.

```text
const makhlukGhaib = {
   nama: 'Pocong',
   kekuatan: 'Terbang',
   attack() {
       console.log('Senyum');
   }
};
 
const benda = {
   nama: 'kompor',
   bahan: 'besi',
   actionName: 'Memanaskan',
   action() {
       console.log(this.actionName);
   }
};
 
const halGhaibLain = {
   nama: 'cinta',
   bahan: 'perjuangan bersama',
   actionName: 'Membara',
   action() {
       console.log(this.actionName);
   }
};
```

## **Question 2**

Import _named export_ berikut ini dengan alias AliasNamed.

```text
 // Anda sedang berada di satu directory dengan nama file contoh.js
 export class NamedExport {
     constructor(test){
         this.test = test;
     }
 }
```

## **Question 3**

Dapatkah kita mengimport suatu module dari luar project directory ? Lalu apa pengaruhnya untuk saat production ?

## **Question 4**

Pada code di bawah ini, lakukan _export_ suatu function tersebut menjadi _export default_ dengan tanpa mengubah sedikit pun code pada function tersebut \(note: Anda dapat menambahkan/mengubah code diatas atau dibawah function, namun bukan pada function, meski hanya mengubah nama function\).

```text
function helloCat() {
   alert('Hello Cat !!');
}
```

## **Question 5**

Berikut ini terdapat sebuah module yang di-_export_ dengan _default_. Lakukan import pada module ini dengan menjadikannya _named_ pada proses import nya. Catatan: Anda sedang berada di directory yang sama dengan file user.js

```text
// folder berada di user.js
export default class User {
   constructor(name) {
       this.name = name;
   }
}
```

