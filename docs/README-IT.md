[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | **Italiano** | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Installatore di Linux Chroot

Installatore di chroot Linux senza sistema e script di avvio chroot Linux

## Requisiti
- Root con Magisk
- busybox installato
- coreutils per make_image
- mke2fs per make_image
- Questo modulo

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## AVVISO
A causa di molti casi come [questo](https://github.com/FerryAr/lhroot/issues/18) e [questo](https://github.com/FerryAr/lhroot/issues/21), assicurati che TUTTI i punti di montaggio nella cartella chroot siano SMONTATI prima di rimuovere la cartella chroot. Non sono responsabile per la perdita di dati, il danneggiamento del telefono, ecc. Puoi verificare in questo repository che tutto il codice che ho scritto non mira intenzionalmente a rimuovere i tuoi dati o a danneggiare il tuo telefono. Usa questo modulo se sei familiare con l'ambiente Linux. Usalo a tuo rischio e pericolo!

## Utilizzo

```console
lhroot
```

e segui le istruzioni.

Dopo l'installazione, per avviare il Linux Chroot, usa:

```console
bootlinux
```

Dalla versione v2.1, puoi eseguire 2 o più istanze di chroot, basta specificare la cartella chroot, ad esempio:

```console
bootlinux /data/manjaro
```

Per smontare la directory bind, usa:

```console
killlinux
```

Dalla versione v2.1, puoi terminare una specifica istanza, basta specificare la cartella chroot, ad esempio:

```console
killlinux /data/manjaro
```

Per creare un'immagine, usa:

```console
make_image <percorso dell'immagine> <nome_immagine.img> <dimensione dell'immagine in MB>
```

Per montare un'immagine, usa:

```console
mount_image <percorso dell'immagine> <percorso della directory Linux>
```

## Distro Disponibili
- Alpine Linux, installata in /data/alpine
- Arch Linux, installata in /data/arch
- Debian, installata in /data/debian
- Fedora, installata in /data/fedora
- Kali Linux, installata in /data/kali
- Manjaro ARM, installata in /data/manjaro
- Ubuntu, installata in /data/ubuntu
- Void Linux, installata in /data/void

...altre distro saranno aggiunte presto

## Architetture Supportate
- arm
- aarch64
- x86
- x64

## DA FARE
- [ ] Migrare tutti i file usati in lhroot al mio repository (WIP)
- [ ] Supporto Audio integrato
- [ ] Compilazione incrociata di tutte le dipendenze

## Crediti
- [mod-util](https://github.com/veez21/mod-util) di @veez21
- Magisk di @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Licenza
Licenziato sotto GNU GPL v3

~~Il file tarball rootfs è preso dalle [Risorse del repository](https://github.com/EXALAB/Anlinux-Resources) di AnLinux~~
La maggior parte dei tarball rootfs delle distro sono stati ricostruiti e memorizzati su [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Supporto
- Apri un problema qui
- o visita il [Thread su XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Nota
- Se desideri memorizzare il tuo chroot in un file immagine, crea prima il file immagine utilizzando make_image, quindi monta l'immagine utilizzando lo script mount_image.
- coreutils può essere installato tramite il modulo [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) di @Zackptg5.
- mke2fs può essere installato tramite il mio [modulo e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), supporto solo per dispositivi arm; altre architetture utilizzeranno l'applet mke2fs di busybox, utilizzeranno il filesystem ext2 e saranno limitate a 2GB di dimensione dell'immagine.