---
description: >-
  Halo semua, project yang akan dibuat pada kesempatan kali ini adalah cek kata.
  Project ini dibuat dengan menggunakan lumen dan react js.
---

# Membuat Backend

### Install backend lumen \(micro framework\)

* install : composer create-project --prefer-dist laravel/lumen backend

### Install sastrawi  

* Install vendor : composer require sastrawi/sastrawi:^1
* Docs           : [https://github.com/sastrawi/sastrawi](https://github.com/sastrawi/sastrawi)

### Install CORS

* Install CORS   : composer require fruitcake/laravel-cors
* Settings CORS :
  * Create config folder
  * Create cors.php inside config folder
  * Add this in bootstrap/app.php

    ```php
      $app->register(Fruitcake\Cors\CorsServiceProvider::class);
      $app->configure('cors');
      $app->middleware([
          Fruitcake\Cors\HandleCors::class,
      ]);
    ```
* Follow this video

