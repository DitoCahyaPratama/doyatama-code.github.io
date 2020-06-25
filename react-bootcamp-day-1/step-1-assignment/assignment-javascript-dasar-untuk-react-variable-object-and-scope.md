---
description: >-
  Sebelum kalian mengerjakan assignment alangkah baiknya kalian untuk
  mempelajari apa itu javascipt dasar untuk react seperti variable, object dan
  scope.
---

# Assignment - JavaScript Dasar untuk React - Variable, Object & Scope

Tapi...... jika kalian sudah mempelajarinya yukk .. kalian bisa langsung check assignment nya .... Selamat Mengerjakan :\)

## **Question 1**

Pada code di bawah ini terdapat sebuah object “sebuahObject” yang memiliki elemen sebuah fungsi, tuliskan code Anda untuk membuat console mengeluarkan log “Hai Dunia Kucing!!” dengan mengakses fungsi tersebut ? Jelaksan!

```text
const sebuahObject = {
    fungsi: () => {
        console.log('Hai Dunia Kucing!!')
    }
}
```

## **Question 2**

Perhatikan code  di bawah ini.

```text
let sebuahVariabel = 'apple'
let sebuahVariabel = 'orange' // SyntaxError: Identifier 'sebuahVariabel ' has already been declared
console.log(sebuahVariabel)
```

Pada line kedua code di atas akan memunculkan error bahwa variabel “sebuahVariabel ” sudah dideklarasikan dengan _let_, tidak dapat dideklarasikan kembali.

```text
var sebuahVariabel = 'apple'
var sebuahVariabel = 'orange'
console.log(sebuahVariabel)
```

Namun, jelaskan kenapa ketika kita ganti _let_ dengan _var_ seperti code di atas ini, tidak ada error yang terjadi!

## **Question 3**

Jelaskan, jika memang _const_ membuat sebuah variable tidak bisa di-_assign_ kembali valuenya, kenapa pada code di bawah ini, masih tetap berlaku ?

```text
const sebuahVariabel  = {}
sebuahVariabel.color = 'red'
```

## **Question 4**

Pada code di bawah ini, kenapa console memberikan output undefined ?

```text
var haloHalo = 1
var haloHaloBandung = function() {
  console.log(haloHalo)
  var haloHalo = 2
}
haloHaloBandung()
```

#### Referensi <a id="referensi"></a>

* \[Hoisting\] [https://scotch.io/tutorials/understanding-hoisting-in-javascript](https://scotch.io/tutorials/understanding-hoisting-in-javascript)
* \[Deep equal\] [https://www.mattzeunert.com/2016/01/28/javascript-deep-equal.html](https://www.mattzeunert.com/2016/01/28/javascript-deep-equal.html)
* \[Deep equal\] [https://www.w3schools.com/nodejs/met\_assert\_deepequal.asp](https://www.w3schools.com/nodejs/met_assert_deepequal.asp)

