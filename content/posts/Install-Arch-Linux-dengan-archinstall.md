---
title: "Install Arch Linux dengan archinstall"
date: 2023-07-08T00:00:00+07:00
tags: ["Arch Linux", "id", "archinstall"]
author: "Me"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Di artikel ini kita akan bahas cara install Arch Linux tanpa manual/cara tradisional seperti yang sering digunakan orang-orang, tetapi kita akan menggunakan cara yang sangat sederhana hanya dengan menggunakan script archinstall kita dapat menghemat waktu untuk instalasinya"
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
editPost:
    URL: "https://github.com/riparuk/riparuk.github.io/content/posts/Install-Arch-Linux-dengan-archinstall.md"
    Text: "Suggest Changes"
    appendFilePath: true
---


Arch Linux adalah salah satu distro linux yang paling populer dan keunggulannya menurut saya adalah [aur](https://wiki.archlinux.org/title/Arch_User_Repository) yang dimilikinya dan kelengkapan dari [wiki](https://wiki.archlinux.org/) nya sendiri, hampir semua hal sudah ada di wikinya mulai dari cara configurasi, instalasi, tips, dan sebagainya menjadi keunggulan dari Arch Linux itu sendiri.

Saya dulu termasuk orang yang sering mencoba beberapa varian dari Linux, disana ada linux mint, LXDE, XFCE, macem-macem lah, dan yang terakhir sampai saat artikel ini ditulis saya jatuh cinta sama **Arch Linux** xD. 

Namun, ada satu kondisi yang membuat saya merasa malas adalah instalasi dari Arch Linux sendiri yang menurut saya **sangat ribet**, banyak hal yang perlu kita configurasi, mulai dari persiapan partisi, format ini itu, set ini itu, yang menurut saya lumayan menyita banyak waktu.

Taklama setelah itu, saya menemukan sebuah cara yang sangat mudah untuk install Arch Linux, tidak perlu manual lagi, yaitu hanya dengan menggunakan script [archinstall](https://github.com/archlinux/archinstall).

Archinstall adalah skrip yang ada dalam distribusi Arch Linux yang bertujuan untuk memudahkan proses instalasi sistem operasi Arch Linux. Skrip ini menyediakan antarmuka yang lebih sederhana dan terstruktur untuk mengatur partisi, menginstal paket-paket, mengatur pengaturan dasar, dan konfigurasi lainnya yang diperlukan saat menginstal Arch Linux.

Dengan menggunakan skrip archinstall, kita dapat melakukan instalasi Arch Linux dengan lebih cepat dan efisien tanpa harus melakukan semua langkah secara manual. Skrip ini menyediakan opsi-opsi yang dapat dikonfigurasi untuk menyesuaikan instalasi sesuai dengan kebutuhan pengguna.

Caranya cukup mudah, ada beberapa hal yang perlu dipastikan sebelum memulai menggunakan *archinstall*
- **Pertama**, pastikan bahwa kamu telah menyiapkan disk yang akan diinstall Arch Linux nya, <span style="color:red"> *Pada tutorial kali ini kita akan melakukan instalasi fresh ke dalam disk, jadi jika ada data penting di dalam disk, pastikan sudah di backup ya... karena nantinya saat instalasi disk akan di format(jadi data di dalamnya akan dihapus)* </span>
- **Kedua** Pastikan kamu telah mengunduh dan menyiapkan file ISO Arch Linux yang terbaru. Setelah melakukan booting ke Arch Linux dari media bootable(seperti USB flash drive) yang telah terisi ISO Arch Linux tadi(*untuk cara buatnya bisa dengan **rufus**,**ventoy**, dsb *), kemudian koneksikan ke jaringan internet, bisa wifi seperti menggunakan [iwctl](https://wiki.archlinux.org/title/iwd) atau ethernet. Karena nantinya kita membutuhkan akses internet untuk mendownload package-package yang dibutuhkan saat instalasi, untuk cara lebih lengkapnya teman-teman bisa cari sendiri seperti [disini](https://wiki.archlinux.org/title/iwd), youtube, atau artikel favorite teman-teman.

Setelah dua cara tersebut sudah dilakukan,
- kita bisa langsung menjalankan perintah **archinstall** di cli arch linux nya.

```
    Set/Modify the below options

    > Archinstall language               set: English (100%)
    Keyboard layout                    set: us
    Mirror region                      set: []
    Locale language                    set: en_US
    Locale encoding                    set: utf-8
    Drive(s)
    Bootloader                         set: systemd-bootctl
    Swap                               set: True
    Hostname                           set: archlinux
    Root password                      set: None
    User account
    Profile                            set: None
    Audio                              set: None
    Kernels                            set: ['linux']
    Additional packages                set: []
    Network configuration              set: Not configured, unavailable unless setup manually
    Timezone                           set: UTC
    Automatic time sync (NTP)          set: True
    Optional repositories              set: []

    Save configuration
    Install (2 config(s) missing)
    Abort
    (Press "/" to search)
```

- Kemudian atur konfigurasi sesuai preferensi. Preferensi saya biasanya : 
    - Archinstall language  : **English (100%)**
    - Keyboard Layout       : **us**
    - Mirror region         : **[]**
    - Locale language       : **en_US**
    - Locale encoding       : **utf-8**
    - Drive(s)              : Pilih drive yang mau diinstall linux nya
    - Disk layout           : Wipe all (semua data di dalam drive yang dipilih akan dihapus)
    - Bootloader            : **systemd-bootctl** atau **GRUB** (bebas sesuai preferensi, saya lebih suka systemd-bootctl)
    - Hostname              : masukkan hostname(bebas, contoh kalau saya biasanya "arch" saja)
    - Root password         : None (saya lebih prefer menggunakan sudo)
    - User account          : Pilih **"Add a user"**, **masukkan username**(bebas, contoh kalau saya "ripa"), **kemudian tekan enter**, **masukkan password**, Should "ripa" be a superuser(sudo)? **pilih yes** dan enter, kemudian **pilih "confirm and exit"**
    - Profile               : Sesuai preferensi, jika ingin menggunakan KDE desktop maka pilih **desktop->kde**, graphics driver sesuai sama perangkat
    - Audio                 : Bebas, saya prefer **pipewire**
    - Kernel                : Bebas, saya biasanya hanya **['linux']**
    - Additional package    : Bebas, saya biasanya hanya browser seperti chromium
    - Network configuration : Saya menggunakan **"Use NetworkManager"**
    - Timezone              : **Asia/Jakarta**
    - Automatic time sync   : **True**
    - Optional repositories : biasanya hanya **['multilib]** agar bisa install steam
    - Setelah semua dikonfiurasi, **pilih "Install"**
    - Tunggu hingga proses selesai, kemudian **reboot** :)



