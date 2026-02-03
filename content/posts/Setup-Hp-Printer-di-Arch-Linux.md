---
title: "Setup HP Printer di Arch Linux"
date: 2023-06-21T00:00:00+07:00
tags: ["Linux", "id"]
author: "Me"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Di artikel ini kita akan bahas secara singkat cara setup printer merk HP yang telah aku coba di Arch Linux"
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
editPost:
    URL: "https://github.com/riparuk/riparuk.github.io/content/posts/Setup-Hp-Printer-di-Arch-Linux.md"
    Text: "Suggest Changes"
    appendFilePath: true
---


Langkah-langkah setup printer HP:
1. Pasang CUPS: gunakan perintah `sudo pacman -S cups`
2. Aktifkan dan buat otomatis (mulai saat boot) layanan pencetakan CUPS: gunakan perintah `sudo systemctl enable --now cups` (nama unit layanan yang digunakan sebelumnya adalah "org.cups.cupsd")
3. Pasang HP Linux Imaging and Printing: gunakan perintah `sudo pacman -S hplip`
4. Colok USB printer ke laptop dan Pasang plugin driver melalui `sudo hp-setup -i`. Hak root penting di sini, jika tidak akan muncul pesan "error: No device selected/specified or that supports this functionality." saat memilih metode koneksi. Selama pemasangan plugin, pilih opsi default setiap kali.
5. Pasang system-config-printer, alat GUI untuk mengonfigurasi printer. `sudo pacman -S system-config-printer`
6. Mulai system-config-printer dan klik tombol untuk menambahkan printer. Pilih printer Anda dan pilih HPLIP sebagai metode koneksi.
7. Sekarang, system-config-printer seharusnya memungkinkan Anda mencetak halaman uji.
8. Agar aplikasi GTK seperti Evince, Okular, dsb dapat menampilkan printer Anda dalam dialog pencetakan, Anda mungkin perlu juga memasang gtk3.
