---
title: "Cara integrasi/menghubungkan google drive di Linux dengan rclone"
date: 2023-07-08T00:00:00+07:00
tags: ["Linux", "id"]
author: "Me"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Di artikel ini kita akan bahas secara singkat cara mengintegrasikan atau menghubungkan google drive agar bisa diakses langsung di Linux dengan rclone"
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
editPost:
    URL: "https://github.com/riparuk/riparuk.github.io/content/posts/Cara-integrasi-google-drive-di-Linux-menggunakan-rclone.md"
    Text: "Suggest Changes"
    appendFilePath: true
---


Langsung saja, sebelum melakukan konfigurasi pastikan rclone telah di install, cara installnya disesuaikan dengan linux yang dimiliki, karena saya menggunakan arch linux, maka tinggal ```sudo pacman -S rclone```.

Pertama kita membuat remote google drivenya terlebih dahulu, cara nya
- Untuk mengonfigurasinya, cukup jalankan ```rclone config``` di terminal.
- pilih `n) New remote`, ketik `n` lalu enter.
- Masukkan nama remote, contoh nama remote saya "gdrive-ripa", kemudian enter.
- Pilih Google Drive, di saya no 18 dan kemudian enter.
- untuk client_id dan client_secret press enter saja, saya tidak menggunakannya.
- Option scope saya pilih "Full access all files,...(drive)", di saya no 1 kemudian enter.
- untuk service_account_file, press enter saja. 
- Edit advance config?, saya pilih `n) No`, ketik `n` lalu enter.
- Use web browser to automatically authenticate rclone with remote? ketik `y` lalu enter. ini akan membuka halaman baru di browser untuk memberikan akses google drivenya kepada rclone, pilih atau login akun yang ingin digunakan.
- Configure this as a Shared Drive (Team Drive)?, saya pilih `n) No`, ketik `n` lalu enter.
- Configuration complete, Keep this "gdrive-ripa" remote?, jika sudah benar pilih `y) Yes this is OK`, ketik `y` lalu enter.
- remote "gdrive-ripa" telah dibuat.
    ```
    Current remotes:

    Name                 Type
    ====                 ====
    gdrive-ripa          drive

    e) Edit existing remote
    n) New remote
    d) Delete remote
    r) Rename remote
    c) Copy remote
    s) Set configuration password
    q) Quit config
    e/n/d/r/c/s/q> q
    ```

- Setelah remote dibuat, kamu bisa keluar konfigurasi, ketik `q` lalu enter atau `ctrl+c`.


Agar bisa mengakses remote yang telah dibuat tadi, kita bisa langsung menggunakan mount yang disediakan oleh rclone, 
- sebelum itu siapkan folder kosong yang ingin digunakan untuk mengakses google drive remote nya, saya melakukan `mkdir ~/Google-Drive` di terminal untuk membuat folder. 
- Kemudian ketik perintah seperti berikut
    ```
    ripa@arch:[~]$ rclone mount gdrive-ripa: ~/Google-Drive/
    ``` 
    di terminal dan hit enter untuk melakukan mount remote `gdrive-ripa` yang telah dibuat ke folder `~/Google-Drive/` yang juga telah dibuat.
- mount telah berhasil, jangan tutup terminal yang sedang berjalan perintah diatas, karena perintah tersebut tidak berjalan di latar belakang. Kamu bisa cek isi dari folder nya, folder di saya tadi `~/Google-Drive/`.
- Jika isinya sesuai dengan isi google drive, maka kamu berhasil.
- Untuk melakukan unmount, kamu bisa menutup terminal atau `ctrl+c` yang sedang berjalan perintah `rclone mount` tersebut.
- Jika ingin menjalankannya dilatar belakang maka bisa menambahkan `&` di akhir perintah tersebut, seperti
    ```
    ripa@arch:[~]$ rclone mount gdrive-ripa: ~/Google-Drive/ &
    ```
   




