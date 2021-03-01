---
description: >-
  Bab ini akan membahas tentang memulai dengan Git. Kita akan mulai dengan
  menjelaskan beberapa latar belakang pada peralatan versi kontrol ,
---

# Git

## Apa itu versi kontrol ?

Apa itu _versi kontrol_ dan apakah penting? _versi kontrol_ adalah suatu sistem yang mengubah-perubahan dari suatu file atau sekumpulan file dari waktu ke waktu sehingga Anda dapat menilik versi khusus dari suatu saat nanti. Sebagai contoh, pada buku ini Anda akan menggunakan sumber kode perangkat lunak untuk file-file yang mendukung dengan _versi kontrol_ , walau pada persetujuan Anda dapat melakukan ini dengan semua jenis file pada komputer.

Untuk lebih jelasnya anda dapat mengecek pada web berikut ini : 

{% embed url="https://git-scm.com/book/id/v2/Memulai-Tentang-Version-Control" %}

## Membuat project Git dan mengelolanya

Pada sesi react native ini kita akan menggunakan `Gitlab` sebagai version control nya. Mari ikuti step-stepnya. 

Pastikan telah terinstall git di komputer anda, jika belum silahkan anda install git terlebih dahulu pada link berikut ini

{% embed url="https://git-scm.com/downloads" %}

Untuk cara installasinya anda dapat mengecek pada link berikut ini :

{% embed url="https://www.digitalocean.com/community/tutorials/how-to-contribute-to-open-source-getting-started-with-git" %}

Jika sudah menginstall git, yuk..... saatnya lanjut ke step selanjutnya.

## Membuat Repository Baru

Repository atau repo di Gitlab biasa disebut dengan project. So, berikut langkah-langkah untuk membuat repository baru:

* Setelah login anda akan menuju halaman Projects yang berisi semua repository yang anda miliki. Jika Anda user baru maka belum ada repository yang tersedia. Di halaman tersebut anda akan melihat tombol New Project di sebelah kanan atas. Klik tombol tersebut.
* Pada halaman membuat project baru, isi kolom project-name dengan nama yang Anda inginkan, misalkan: my first repo.
* Pada kolom visibility level Anda akan melihat tiga pilihan yaitu Private, Internal, dan Public. Private artinya repo yang akan kita buat bersifat rahasia, hanya Anda dan orang yang Anda beri akses saja yang bisa membukanya. Sedangkan pilihan Internal berarti repo Anda akan dapat dilihat oleh semua user Gitlab. Pilihan “Public” berarti repo Anda akan terlihat oleh orang dari mana saja walaupun dia tidak memiliki akun gitlab. Pilih yang sesuai kebutuhan misalkan : Public.
* Di bagian bawahnya terdapat pilihan checkbox “Initialize repository with a README”. Centang saja jika anda ingin langsung clone repository nya setelah dibuat.
* Jika berhasil maka Anda akan diarahkan menuju halaman project atau repo yang telah dibuat. Jika sebelumnya kita centang “Initialize repository with a README” maka repository kita akan berisi file README.md.
* Pada Bagian kanan atas terdapat tombol clone. Ketika diklik maka akan keluar dua pilihan “Clone with SSH” dan “Clone with HTTPS”. Pilih saja clone dengan HTTPS. Klik tombol salin/copy supaya langsung otomatis tercopy pada clipboard. Jika ingin clone dengan SSH maka anda harus setting dulu akun anda agar terhubung dengan komputer Anda.
* Setelah itu menuju ke terminal atau cmd. Arahkan menuju folder dimana anda ingin menyimpan repository yang sudah Anda buat. Berikan perintah git clone &lt;link\_anda\_yang\_barusan\_dicopy&gt; \(tanda &lt;&gt; hanyalah sebagai penanda template tidak usah ditulis di perintah cmd\)

  ```text
  $ git clone <your_repository_link_url>
  ```

* Jika sudah berhasil diclone maka akan ditemukan folder dengan nama repository di Gitlab. Cara mengeceknya dengan perintah “ls” atau “dir”.

  ```text
  $ ls
  my-first-repo   
  ```

#### Mengupload perubahan project dengan git push <a id="mengupload-perubahan-project-dengan-git-push"></a>

Ketika kita sudah berhasil clone repository kita di Gitlab maka tentu kita ingin melakukan update atau penambahan code pada project kita. Agar perbaruan yang kita simpan di local \(komputer\) kita dapat kita perbaharui juga di repository Gitlab maka kita bisa lakukan dengan git push. Berikut langkah-langkahnya:

* Ketika kita sudah memberikan perubahan terhadap suatu file atau membuat folder-folder baru pada folder project kita maka cara mengecek status perbaruan adalah dengan git status

```text
$ git status
On branch master
Your branch is up to date with 'origin/master'.
 
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
 
 modified:   README.md
 
no changes added to commit (use "git add" and/or "git commit -a") 
```

* Setelah git status maka akan ditampilkan list file yang “modified” atau “untracked”. “modified” artinya adalah kita mengubah file yang sebelumnya ada sedangkan “untracked” artinya file tersebut sama sekali baru di repository. Dalam contoh di atas terdapat perubahan pada file “README.md”.
* Untuk menaikkan perubahan \(stage\) yang kita buat maka berikan perintah git add

```text
$ git add README.md

// Jika ada terdapat banyak file dan kita ingin naikkan semuanya maka perintahnya: 
$ git add .  
```

* Sekarang perubahan tadi sudah pada tahap “staged”. jika kita cek status nya lagi maka akan didapati berbeda:

```text
$ git status 
On branch master
Your branch is up to date with 'origin/master'.
 
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)
 
 modified:   README.md 
```

* Selanjutnya adalah memberikan laporan atau commit terhadap perubahan yang kita buat dengan git commit.

```text
 $ git commit -m "Pesan saya: Mengubah README.md"
```

* tanda “-m” pada perintah commit artinya kita ingin memberikan pesan atau laporan terhadap perubahan yang sudah dibuat. Dalam hal ini laporannya adalah “Pesan saya: mengubah README.md”
* Selanjutnya adalah push untuk mengirim /upload perubahan yang ada di local computer kita menuju repository yang ada di Gitlab. Jika kita berada di branch bernama master maka perintahnya adalah:

```text
$ git push origin master 
```

Jika branch yang sedang kita miliki di local adalah branch lain selain master maka cara push nya adalah

```text
$ git push origin <nama_branch>
```

Jika langkah tersebut sudah maka kita sudah berhasil mengupload perubahan yang kita buat di repository kita. 🥂

### Git branch dan merge request <a id="git-branch-dan-merge-request"></a>

Membuat branch baru dan melakukan merge request

#### Clone repository <a id="clone-repository"></a>

Terlebih dahulu lakukan clone terhadap repository project.

```text
$ git clone https://gitlab.com/some-project 
$ cd some-project
```

Catatan: Link https di atas hanyalah contoh link dari sebuah repository. Link https tersebut bisa diperoleh di halaman gitlab pada bagian clone.

#### Buat branch baru <a id="buat-branch-baru"></a>

Setelah di-clone dan masuk ke folder project nya, buatlah branch baru . \(myname hanyalah contoh nama branch, kita bisa mengubah sesuai nama yang diinginkan\)

```text
$ git branch myname
$ git checkout myname 
```

maka sekarang kita sudah berada di branch baru dan dapat mulai melakukan pekerjaan kita.

> Catatan:
>
> `myname` hanya contoh , silakan sesuaikan sendiri nama branch masing-masing.

#### Push ke branch  <a id="push-ke-branch"></a>

Setelah pekerjaan selesai, kita akan melakukan upload atau push ke branch kita sendiri.

```text
$ git add . 
$ git commit -m "some message"// push ke branch 
$ git push origin myname
```

> Catatan:
>
> `"some message"` hanyalah contoh pesan atau komentar pada sebuah commit. Silahkan isi dengan jenis update yang dikerjakan.

#### Membuat merge request <a id="membuat-merge-request"></a>

Setelah melakukan push ke branch sendiri maka selanjutnya melakukan merge request.

Secara default pada halaman project akan tersedia tombol “create merge request”.![](https://gblobscdn.gitbook.com/assets%2F-LlUaK30_GFBvMOdUWKf%2F-LldepAZorMgXgsf4exP%2F-Lldo6E7VUbbizSnzZRM%2Fmerge-request.jpeg?alt=media&token=672f6a87-a9ad-4b11-a72c-d03bc6a820c2)

Jika tombol tersebut tersedia, klik tombol tersebut untuk menuju halaman merge request.

Pada halaman merge request isilah kolom title dengan pesan commit atau laporan progress pekerjaan misalkan : done, work in progress atau WIP, dsb.![](https://gblobscdn.gitbook.com/assets%2F-LlUaK30_GFBvMOdUWKf%2F-LldepAZorMgXgsf4exP%2F-LldpcFElD1xcptGIuSF%2Ftitle%20merge-request.jpeg?alt=media&token=e97935be-d331-420a-9fb5-ec74fb539608)

Setelah itu, klik submit merge request maka pekerjaan kita sudah disubmit ke merge request dan akan direview oleh pengelola project.

Selengkapnya kamu bisa ikuti juga video tutorial berikut ini:

