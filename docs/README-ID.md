[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | **Indonesian**


# Installer Linux Chroot

Instalator Linux chroot tanpa sistem dan skrip boot Linux chroot

## Persyaratan
- Root dengan Magisk
- busybox terinstal
- coreutils untuk make_image
- mke2fs untuk make_image
- Modul ini

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## PERHATIAN
Karena banyak kasus seperti [ini](https://github.com/FerryAr/lhroot/issues/18) dan [ini](https://github.com/FerryAr/lhroot/issues/21), pastikan SEMUA titik mount di folder chroot DIBERHENTIKAN sebelum menghapus folder chroot. Saya tidak bertanggung jawab atas kehilangan data, kerusakan ponsel, dll. Anda dapat memeriksa repositori ini bahwa semua kode yang saya tulis tidak dengan sengaja menghapus data Anda atau merusak ponsel Anda. Gunakan modul ini jika Anda sudah familiar dengan lingkungan Linux. DWYOR!

## Penggunaan

```console
lhroot
```

dan ikuti petunjuknya.

Setelah instalasi, untuk boot ke Linux Chroot gunakan:

```console
bootlinux
```

Setelah v2.1, Anda dapat menjalankan 2 atau lebih instansi chroot, cukup berikan folder chroot, misalnya:

```console
bootlinux /data/manjaro
```

Untuk melepaskan direktori bind gunakan:

```console
killlinux
```

Setelah v2.1, Anda dapat menghentikan instansi tertentu, cukup berikan folder chroot, misalnya:

```console
killlinux /data/manjaro
```

Untuk membuat gambar gunakan:

```console
make_image <path ke img> <nama_img.img> <ukuran img dalam MB>
```

Untuk memasang gambar gunakan:

```console
mount_image <path ke img> <path ke direktori linux>
```

## Distribusi Tersedia
- Alpine Linux, diinstal di /data/alpine
- Arch Linux, diinstal di /data/arch
- Debian, diinstal di /data/debian
- Fedora, diinstal di /data/fedora
- Kali Linux, diinstal di /data/kali
- Manjaro ARM, diinstal di /data/manjaro
- Ubuntu, diinstal di /data/ubuntu
- Void Linux, diinstal di /data/void

...distribusi lainnya akan ditambahkan segera

## Arsitektur yang Didukung
- arm
- aarch64
- x86
- x64

## TODO
- [ ] Migrasikan semua file yang digunakan di lhroot ke repositori saya (WIP)
- [ ] Dukungan audio bawaan
- [ ] Kompilasi silang semua dependensi

## Penghargaan
- [mod-util](https://github.com/veez21/mod-util) oleh @veez21
- Magisk oleh @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Lisensi
Lisensi di bawah GNU GPL v3

~~Tarball rootfs diambil dari [AnLinux Resources Repository](https://github.com/EXALAB/Anlinux-Resources)~~
Sebagian besar tarball rootfs distribusi telah dibangun ulang dan disimpan di [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Dukungan
- Buka masalah di sini
- atau kunjungi [XDA Thread](https://forum.xda-developers.com/showthread.php?t=4142803)

## Catatan
- Jika Anda ingin menyimpan chroot Anda dalam file gambar, buat file gambar terlebih dahulu menggunakan make_image dan kemudian pasang gambar menggunakan skrip mount_image.
- coreutils dapat diinstal melalui modul [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) dari @Zackptg5.
- mke2fs dapat diinstal melalui [modul e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm) saya, hanya mendukung perangkat arm; arsitektur lain akan menggunakan applet mke2fs dari busybox, menggunakan sistem file ext2, dan terbatas pada ukuran gambar 2GB.