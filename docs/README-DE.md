[English](README.md) | [العربية](README-AR.md) | **Deutsch** | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Linux Chroot Installer

Systemloser Linux Chroot-Installer und Linux Chroot-Boot-Skript

## Anforderungen
- Mit Magisk gerootet
- busybox installiert
- coreutils für make_image
- mke2fs für make_image
- Dieses Modul

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## HINWEIS
Aufgrund vieler Fälle wie [diesem](https://github.com/FerryAr/lhroot/issues/18) und [diesem](https://github.com/FerryAr/lhroot/issues/21), stellen Sie bitte sicher, dass ALLE Mount-Punkte im Chroot-Ordner VOR dem Entfernen des Chroot-Ordners AUSSER BETRIEB genommen werden. Ich übernehme keine Verantwortung für Datenverluste, das Bricken des Telefons usw. Sie können in diesem Repository nachsehen, dass der gesamte von mir geschriebene Code nicht beabsichtigt, Ihre Daten zu löschen oder Ihr Telefon zu bricke. Verwenden Sie dieses Modul, wenn Sie mit der Linux-Umgebung vertraut sind. Benutzung auf eigene Gefahr!

## Verwendung

```console
lhroot
```

und folgen Sie den Anweisungen.

Nach der Installation, um in Linux Chroot zu starten, verwenden Sie:

```console
bootlinux
```

Nach v2.1 können Sie 2 oder mehr Chroot-Instanzen ausführen, geben Sie einfach den Chroot-Ordner an, z.B.:

```console
bootlinux /data/manjaro
```

Um das gebundene Verzeichnis zu unmounten, verwenden Sie:

```console
killlinux
```

Nach v2.1 können Sie eine spezifische Instanz beenden, geben Sie einfach den Chroot-Ordner an, z.B.:

```console
killlinux /data/manjaro
```

Um ein Image zu erstellen, verwenden Sie:

```console
make_image <Pfad zur img> <img_name.img> <img-Größe in MB>
```

Um ein Image zu mounten, verwenden Sie:

```console
mount_image <Pfad zur img> <Pfad zum Linux-Verzeichnis>
```

## Verfügbare Distributionen
- Alpine Linux, installiert unter /data/alpine
- Arch Linux, installiert unter /data/arch
- Debian, installiert unter /data/debian
- Fedora, installiert unter /data/fedora
- Kali Linux, installiert unter /data/kali
- Manjaro ARM, installiert unter /data/manjaro
- Ubuntu, installiert unter /data/ubuntu
- Void Linux, installiert unter /data/void

...weitere Distributionen werden bald hinzugefügt

## Unterstützte Architekturen
- arm
- aarch64
- x86
- x64

## TODO
- [ ] Alle in lhroot verwendeten Dateien in mein Repository migrieren (WIP)
- [ ] Eingebaute Audio-Unterstützung
- [ ] Cross-Compilation aller Abhängigkeiten

## Dank
- [mod-util](https://github.com/veez21/mod-util) von @veez21
- Magisk von @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Lizenz
Lizenziert unter GNU GPL v3

~~Das rootfs-Tarball wurde aus dem [AnLinux Resources Repository](https://github.com/EXALAB/Anlinux-Resources) entnommen~~
Die meisten Tarballs des rootfs der Distributionen wurden neu gebaut und im [lhroot-repo](https://github.com/FerryAr/lhroot-repo) gespeichert

## Unterstützung
- Eröffnen Sie hier ein Problem
- oder besuchen Sie [XDA-Thread](https://forum.xda-developers.com/showthread.php?t=4142803)

## Hinweis
- Wenn Sie Ihr Chroot in einer Image-Datei speichern möchten, erstellen Sie zuerst die Image-Datei mit make_image und mounten Sie dann das Image mit dem Skript mount_image.
- coreutils kann über das [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) Modul von @Zackptg5 installiert werden.
- mke2fs kann über mein [e2fsprogs Modul](https://github.com/FerryAr/e2fsprogs-arm) installiert werden, nur Unterstützung für arm-Geräte; andere Architekturen verwenden die mke2fs-Applets von busybox, verwenden das ext2-Dateisystem und sind auf eine Imagegröße von 2 GB begrenzt.