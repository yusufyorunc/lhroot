[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | **Français** | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Installateur Linux Chroot

Installateur chroot Linux sans système et script de démarrage chroot Linux

## Exigences
- Rooté avec Magisk
- busybox installé
- coreutils pour make_image
- mke2fs pour make_image
- Ce module

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## AVIS
En raison de nombreux cas comme [celui-ci](https://github.com/FerryAr/lhroot/issues/18) et [celui-ci](https://github.com/FerryAr/lhroot/issues/21), veuillez vous assurer que TOUS les points de montage dans le dossier chroot sont DÉMONTÉS avant de supprimer le dossier chroot. Je ne suis pas responsable de la perte de données, du brickage du téléphone, etc. Vous pouvez vérifier dans ce dépôt que tout le code que j'ai écrit n'a pas pour but de supprimer vos données ou de briquer votre téléphone. Utilisez ce module si vous êtes familiarisé avec l'environnement Linux. Utilisation à vos risques et périls !

## Utilisation

```console
lhroot
```

et suivez les instructions.

Après l'installation, pour démarrer dans Linux Chroot, utilisez :

```console
bootlinux
```

Après la version v2.1, vous pouvez exécuter 2 ou plusieurs instances de chroot, il suffit de passer le dossier chroot, par exemple :

```console
bootlinux /data/manjaro
```

Pour démonter le répertoire lié, utilisez :

```console
killlinux
```

Après la version v2.1, vous pouvez terminer une instance spécifique, il suffit de passer le dossier chroot, par exemple :

```console
killlinux /data/manjaro
```

Pour créer une image, utilisez :

```console
make_image <chemin vers img> <nom_img.img> <taille img en MB>
```

Pour monter une image, utilisez :

```console
mount_image <chemin vers img> <chemin vers le répertoire Linux>
```

## Distributions Disponibles
- Alpine Linux, installé sur /data/alpine
- Arch Linux, installé sur /data/arch
- Debian, installé sur /data/debian
- Fedora, installé sur /data/fedora
- Kali Linux, installé sur /data/kali
- Manjaro ARM, installé sur /data/manjaro
- Ubuntu, installé sur /data/ubuntu
- Void Linux, installé sur /data/void

...plus de distributions seront ajoutées bientôt

## Architectures Supportées
- arm
- aarch64
- x86
- x64

## À FAIRE
- [ ] Migrer tous les fichiers utilisés dans lhroot vers mon dépôt (WIP)
- [ ] Support audio intégré
- [ ] Compilation croisée de toutes les dépendances

## Remerciements
- [mod-util](https://github.com/veez21/mod-util) par @veez21
- Magisk par @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Licence
Licence sous GNU GPL v3

~~Le tarball rootfs est pris depuis le [dépôt AnLinux Resources](https://github.com/EXALAB/Anlinux-Resources)~~
La plupart des tarballs rootfs des distributions ont été reconstruits et stockés dans [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Support
- Ouvrir un problème ici
- ou visitez le [fil de discussion XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Remarque
- Si vous souhaitez stocker votre chroot dans un fichier image, créez d'abord le fichier image en utilisant make_image, puis montez l'image en utilisant le script mount_image.
- coreutils peut être installé via le module [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) de @Zackptg5.
- mke2fs peut être installé via mon [module e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), prise en charge uniquement pour les appareils arm ; d'autres architectures utiliseront les applets mke2fs de busybox, utiliseront le système de fichiers ext2 et seront limitées à une taille d'image de 2 Go.