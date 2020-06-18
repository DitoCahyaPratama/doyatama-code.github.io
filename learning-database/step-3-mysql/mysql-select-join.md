# MySQL - Select JOIN

### Teori <a id="teori"></a>

1. Relationship

   Relationship adalah suatu hubungan antara beberapa entitas. Konsep ini sangat penting sekali di dalam basis data, di mana memungkinkan entitas-entitas untuk saling berhubungan satu sama lain. Di dalam sebuah relationship, primary key memiliki peran penting untuk mengaitkan entitas. Selain itu, primary key juga digunakan untuk mendefinisikan batasan keterhubungan.

2. Join

   Join merupakan salah satu konstruksi dasar dari SQL dan basis data. Join dapat didefinisikansebagai kombinasi record dari dua atau lebih tabel di dalam basis data relasional dan menghasilkan sebuah tabel \(temporary\) baru yang disebut sebagai joined table. Join dapat diklasifikasikan ke dalam dua jenis: inner dan outer.

   * Inner Join

     Inner join pada dasarnya adalah menemukan persimpangan \(intersection\) antara dua buah tabel. Sintaks inner join diperlihatkan sebagai berikut:

     ```text
       SELECT A1, A2, ..., An 
       FROM r1 
       INNER JOIN r2 
       ON r1.join_key = r2.join_key
     ```

     Inner join juga dapat direpresentasikan dalam bentuk implisit.

     ```text
       SELECT A1, A2, ..., An 
       FROM r1, r2 
       WHERE r1.key = r2.key
     ```

     Misalkan terdapat tabel A dan B, maka hasil inner join dapat diperlihatkan—sebagai bidang terarsir—dalam diagram Venn seperti Gambar 1.

     ![Inner Join](https://data.sinaungoding.com/11/images/13-01.png)

     Gambar 1. Inner Join

   * Outer Join
     * Left Outer Join

       Left outer join \(atau left join\) mengembalikan semua nilai dari tabel kiri ditambah dengan nilai dari tabel kanan yang sesuai \(atau NULL jika tidak ada nilai yang sesuai\).

       Sintaks

       ```text
         SELECT A1, A2, ..., An 
         FROM r1 
         LEFT OUTER JOIN r2 
         ON r1.join_key = r2.join_key
       ```

       Left outer join antara tabel A dan B dapat diilustrasikan dalam diagram Venn seperti Gambar 2

       ![Left Outer Join](https://data.sinaungoding.com/11/images/13-02.png)

       Gambar 2. Left Outer Join

       * Right Outer Join

         Right outer join \(atau right join\) pada dasarnya sama seperti left join, namun dalam bentuk terbalik—kanan dan kiri. Sintaks right outer join diperlihatkan sebagai berikut:

         Sintaks

         ```text
         SELECT A1, A2, ..., An 
         FROM r1 
         RIGHT OUTER JOIN r2 
         ON r1.join_key = r2.join_key
         ```

         Right outer join antara tabel A dan B dapat diilustrasikan dalam diagram Venn seperti Gambar 3

         ![Right Outer Join](https://data.sinaungoding.com/11/images/13-03.png)

         Gambar 3. Right Outer Join

       * Full Outer Join

         Full outer join \(atau full join\) pada hakekatnya merupakan kombinasi dari left dan right join. Sintaks full outer join diperlihatkan sebagai berikut:

         Sintaks

         ```text
         SELECT A1, A2, ..., An 
         FROM r1 
         FULL OUTER JOIN r2 
         ON r1.join_key = r2.join_key
         ```

         Bentuk visual dari full outer join dapat diperlihatkan menggunakan diagram Venn seperti Gambar 4.

         ![Full Outer Join](https://data.sinaungoding.com/11/images/13-04.png)

         Gambar 4. Full Outer Join

         Selain empat jenis join yang utama di atas, masih ada beberapa variasi join lainnya, seperti CROSS JOIN \(cartesian product\), NATURAL JOIN, dan sebagainya. Perlu juga diperhatikan, join bisa diimplementasikan dalam bentuk bersarang \(nested join\). Jadi, di dalam sebuah operasi join bisa terdapat operasi join lainnya.

### Praktikum <a id="praktikum"></a>

#### Relationship <a id="relationship"></a>

* Buat database `nama_kantor(isi dengan nama anda)`

  ![](https://data.sinaungoding.com/11/images/image011.png)

* Buat tabel karyawan dan tabel departemen dengan struktur sebagai berikut:

  ```text
    CREATE TABLE karyawan ( nama varchar(30) NOT NULL, id_dep int(5) NOT NULL
    ) ENGINE=MyISAM;

      CREATE TABLE departemen ( id_dep int(5) NOT NULL, nama_dep varchar(30) NOT NULL, PRIMARY KEY (id_dep)
      ) ENGINE=MyISAM;
  ```

  Data yang digunakan adalah sebagai berikut:

  ```text
      Tabel Karyawan
      Nama    id_dep
      Agus    10    
      Budi    16
      Citra    12
      Dani    17

      Tabel Departmen
      id_dep    nama_dep
      10    Penelitian
      11    Pemasaran
      12    SDM
      13    Keuangan
  ```

  ![](https://data.sinaungoding.com/11/images/image014.png)

#### Inner Join <a id="inner-join"></a>

Sebagaimana dijelaskan, inner join akan mengembalikan data di tabel A dan B yang sesuai. Sebagai contoh, kita bisa mendapatkan data karyawan yang memiliki departemen.

* Data karyawan yang memiliki departemen

  Cara 1

  ![](https://data.sinaungoding.com/11/images/image016.png)

  Cara 2

  ![](https://data.sinaungoding.com/11/images/image017.png)

  Dalam pengambilan data ini, kita juga bisa menspesifikasikan field terkait. Sebagai contoh, hanya mengambil nama karyawan dan nama departemen saja.

  ![](https://data.sinaungoding.com/11/images/image018.png)

  Agar penulisan SQL lebih efisien, kita dapat memanfaatkan fitur “ derived table” \(atau alias\).

  ![](https://data.sinaungoding.com/11/images/image019.png)

  Pada pernyataan SQL di atas, tabel karyawan dinotasikan dengan huruf k dan tabel departemen menggunakan huruf d.

  **Outer Join**

* Left Outer Join

  Data seluruh karyawan \(yang memiliki departemen maupun tidak\)

  ![](https://data.sinaungoding.com/11/images/image021.png)

  Data karyawan yang tidak memiliki departemen

  ![](https://data.sinaungoding.com/11/images/image022.png)

* Right Outer Join

  ![](https://data.sinaungoding.com/11/images/image023.png)

* Full Outer Join

  ![](https://data.sinaungoding.com/11/images/image024.png)

* Cross Join

  Cara 1

  ![](https://data.sinaungoding.com/11/images/image026.png)

  Cara 2

  ![](https://data.sinaungoding.com/11/images/image027.png)

