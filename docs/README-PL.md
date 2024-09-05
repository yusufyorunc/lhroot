[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | **Polski** | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md) 


# Instalator Linux Chroot

Instalator Linux chroot bezsystemowy i skrypt uruchamiający Linux chroot

## Wymagania
- Root z Magisk
- busybox zainstalowany
- coreutils do make_image
- mke2fs do make_image
- Ten moduł

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## UWAGA
Ze względu na wiele przypadków, takich jak [ten](https://github.com/FerryAr/lhroot/issues/18) i [ten](https://github.com/FerryAr/lhroot/issues/21), upewnij się, że WSZYSTKIE punkty montowania w folderze chroot są ODPĘTLOWANE przed usunięciem folderu chroot. Nie ponoszę odpowiedzialności za utratę danych, uszkodzenie telefonu itp. Możesz sprawdzić w tym repozytorium, że cały kod, który napisałem, nie ma na celu usunięcia twoich danych lub uszkodzenia telefonu. Używaj tego modułu, jeśli jesteś zaznajomiony z środowiskiem Linux. Używaj na własne ryzyko!

## Użycie

```console
lhroot
```

i postępuj zgodnie z instrukcjami.

Po instalacji, aby uruchomić Linux Chroot, użyj:

```console
bootlinux
```

Od wersji v2.1 możesz uruchomić 2 lub więcej instancji chroot, wystarczy przekazać folder chroot, np.

```console
bootlinux /data/manjaro
```

Aby odmontować katalog powiązany, użyj:

```console
killlinux
```

Od wersji v2.1 możesz zakończyć konkretną instancję, wystarczy przekazać folder chroot, np.

```console
killlinux /data/manjaro
```

Aby stworzyć obraz, użyj:

```console
make_image <ścieżka do obrazu> <nazwa_obrazu.img> <rozmiar obrazu w MB>
```

Aby zamontować obraz, użyj:

```console
mount_image <ścieżka do obrazu> <ścieżka do katalogu Linux>
```

## Dostępne Dystrybucje
- Alpine Linux, zainstalowany w /data/alpine
- Arch Linux, zainstalowany w /data/arch
- Debian, zainstalowany w /data/debian
- Fedora, zainstalowany w /data/fedora
- Kali Linux, zainstalowany w /data/kali
- Manjaro ARM, zainstalowany w /data/manjaro
- Ubuntu, zainstalowany w /data/ubuntu
- Void Linux, zainstalowany w /data/void

...więcej dystrybucji wkrótce

## Obsługiwane Architektury
- arm
- aarch64
- x86
- x64

## TODO
- [ ] Migracja wszystkich plików używanych w lhroot do mojego repozytorium (WIP)
- [ ] Wbudowane wsparcie audio
- [ ] Cross-compilacja wszystkich zależności

## Podziękowania
- [mod-util](https://github.com/veez21/mod-util) by @veez21
- Magisk by @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Licencja
Licencjonowane na podstawie GNU GPL v3

~~Plik tarball rootfs pochodzi z [repozytorium AnLinux Resources](https://github.com/EXALAB/Anlinux-Resources)~~
Większość tarballi rootfs dystrybucji została odbudowana i przechowywana w [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Wsparcie
- Otwórz problem tutaj
- lub odwiedź [wątek XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Uwaga
- Jeśli chcesz przechowywać swój chroot w pliku obrazu, najpierw stwórz plik obrazu używając make_image, a następnie zamontuj obraz używając skryptu mount_image.
- coreutils można zainstalować za pomocą modułu [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) od @Zackptg5.
- mke2fs można zainstalować za pomocą mojego [modułu e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), wsparcie tylko dla urządzeń arm; inne architektury będą używały appletów mke2fs z busybox, będą używały systemu plików ext2 i mają limit rozmiaru obrazu 2GB.