[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | **Türkçe** | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Linux Chroot Kurucu

Sistemless Linux chroot kurucu ve Linux chroot başlatma betiği

## Gereksinimler
- Magisk ile rootlanmış olmalı
- busybox yüklü olmalı
- make_image için coreutils
- make_image için mke2fs
- Bu modül

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## DİKKAT
[Bu](https://github.com/FerryAr/lhroot/issues/18) ve [bu](https://github.com/FerryAr/lhroot/issues/21) gibi birçok durum nedeniyle, chroot klasörünü kaldırmadan önce chroot klasöründeki TÜM bağlama noktalarının UNMOUNT edildiğinden emin olun. Tüm verilerin kaybından, telefonun kullanılmaz hale gelmesinden vb. sorumlu değilim. Bu depoda yazdığım tüm kodları inceleyebilirsiniz, bilerek verilerinizi silmek veya telefonunuzu kullanılmaz hale getirmek gibi bir amacım yok. Linux ortamı hakkında bilgi sahibiyseniz bu modülü kullanın. DWYOR!

## Kullanım

```console
lhroot
```

ve talimatları izleyin.

Kurulumdan sonra Linux Chroot’a geçiş yapmak için:

```console
bootlinux
```

V2.1 sürümünden sonra 2 veya daha fazla chroot örneği çalıştırabilirsiniz, sadece chroot klasörünü girin, örneğin:

```console
bootlinux /data/manjaro
```

Bağlanmış dizini unmount etmek için:

```console
killlinux
```

V2.1 sürümünden sonra belirli bir örneği sonlandırabilirsiniz, sadece chroot klasörünü girin, örneğin:

```console
killlinux /data/manjaro
```

Görüntü oluşturmak için:

```console
make_image <img yolunu girin> <img adı.img> <img boyutu MB olarak>
```

Görüntüyü bağlamak için:

```console
mount_image <img yolunu girin> <linux dizini yolu>
```

## Mevcut Dağıtımlar
- Alpine Linux, /data/alpine dizinine kurulu
- Arch Linux, /data/arch dizinine kurulu
- Debian, /data/debian dizinine kurulu
- Fedora, /data/fedora dizinine kurulu
- Kali Linux, /data/kali dizinine kurulu
- Manjaro ARM, /data/manjaro dizinine kurulu
- Ubuntu, /data/ubuntu dizinine kurulu
- Void Linux, /data/void dizinine kurulu

...daha fazla dağıtım yakında eklenecek

## Desteklenen Mimariler
- arm
- aarch64
- x86
- x64

## YAPILACAKLAR
- [ ] lhroot'da kullanılan tüm dosyaları kendi depoma taşımak (WIP)
- [ ] Dahili Ses desteği eklemek
- [ ] Tüm bağımlılıkları çapraz derlemek

## Katkıda Bulunanlar
- [mod-util](https://github.com/veez21/mod-util) by @veez21
- Magisk by @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Lisans
GNU GPL v3 ile lisanslanmıştır.

~~Kök dosya sistemi tarball'ı AnLinux Resources [Deposu](https://github.com/EXALAB/Anlinux-Resources) üzerinden alınmıştır~~
Birçok dağıtım kök dosya sistemi tarball'ı yeniden oluşturulmuş ve [lhroot-repo](https://github.com/FerryAr/lhroot-repo)'da depolanmıştır.

## Destek
- Buradan sorun açın
- veya [XDA Konusu](https://forum.xda-developers.com/showthread.php?t=4142803)'nu ziyaret edin

## Not
- Eğer chroot'u bir görüntü dosyasında saklamak istiyorsanız, önce make_image kullanarak görüntü dosyasını oluşturun, ardından mount_image betiğini kullanarak görüntüyü bağlayın.
- coreutils, @Zackptg5'in [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) modülü ile kurulabilir.
- mke2fs, sadece arm cihazlar için destek sunan benim [e2fsprogs modülü](https://github.com/FerryAr/e2fsprogs-arm) üzerinden kurulabilir, diğer mimariler busybox mke2fs uygulamalarını kullanacaktır, ext2 dosya sistemi kullanılacak ve 2GB görüntü boyutuyla sınırlı olacaktır.
