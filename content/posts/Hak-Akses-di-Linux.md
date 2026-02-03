---
title: "User,Group dan Hak Akses di Linux"
date: 2023-06-21T00:00:00+07:00
tags: ["Linux", "id"]
author: "Me"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Di artikel ini kita akan bahas secara singkat apa itu User, Group dan hubungan dengan Hak Akses di Linux"
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
editPost:
    URL: "https://github.com/riparuk/riparuk.github.io/content/posts/Hak-Akses-di-Linux.md"
    Text: "Suggest Changes"
    appendFilePath: true
---


Di sistem operasi Linux, pengguna dan hak akses merupakan salah satu konsep penting yang perlu dipahami. Pengguna merupakan individu atau entitas yang terdaftar di sistem operasi dan memiliki hak akses untuk mengakses atau menggunakan resource yang tersedia. Hak akses ini dapat berupa hak akses untuk menjalankan perintah atau mengakses file atau direktori tertentu.

Ada beberapa jenis pengguna di Linux, di antaranya adalah:
- Pengguna biasa (normal user) adalah pengguna yang tidak memiliki hak akses superuser atau root. Pengguna biasa hanya dapat mengakses resource yang diberikan oleh sistem operasi atau yang dapat diakses oleh siapa saja.
- Pengguna superuser atau root adalah pengguna yang memiliki hak akses tertinggi di sistem operasi. Pengguna ini dapat mengakses semua resource yang tersedia di sistem operasi dan memiliki hak akses untuk menjalankan perintah-perintah sistem yang berkaitan dengan konfigurasi atau pengelolaan sistem.

Selain itu, terdapat juga group pengguna di Linux, yaitu kelompok pengguna yang memiliki hak akses yang sama. Group pengguna dapat digunakan untuk mengelompokkan pengguna yang memiliki hak akses yang sama, seperti pengguna yang memiliki hak akses terbatas untuk mengakses file atau pengguna yang memiliki hak akses untuk mengelola server web.

Untuk membuat group pengguna, Anda dapat menggunakan perintah groupadd di terminal. Contohnya:

```
$ groupadd webadmin
```

Perintah ini akan membuat group pengguna bernama webadmin. Anda juga dapat menambahkan pengguna ke group dengan menggunakan perintah usermod di terminal. Contohnya:

```
$ usermod -aG webadmin user1
```

Perintah ini akan menambahkan pengguna user1 ke group pengguna webadmin. Jadi setiap file atau perintah dengan hak akses berdasarkan grub tertentu maka user-user didalam grub tersebut bisa akses filenya.



