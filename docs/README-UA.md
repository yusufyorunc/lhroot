[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | **Українська**| [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Установник Linux Chroot

Установник безсистемного Linux chroot і сценарій завантаження Linux chroot

## Вимоги
- Root з Magisk
- Встановлений busybox
- coreutils для make_image
- mke2fs для make_image
- Цей модуль

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## ПРИМІТКА
Через випадки, як [цей](https://github.com/FerryAr/lhroot/issues/18) та [цей](https://github.com/FerryAr/lhroot/issues/21), переконайтеся, що ВСІ точки монтування в папці chroot ВІДМОНТОВАНІ перед видаленням папки chroot. Я не несу відповідальності за втрату даних, пошкодження телефону тощо. Ви можете перевірити цей репозиторій, що весь код, який я написав, не спрямований на видалення ваших даних або пошкодження вашого телефону. Використовуйте цей модуль, якщо ви знайомі з середовищем Linux. Використовуйте на свій ризик!

## Використання

```console
lhroot
```

і дотримуйтесь інструкцій.

Після встановлення, щоб завантажити Linux Chroot, використовуйте:

```console
bootlinux
```

Починаючи з версії v2.1, ви можете запускати 2 або більше примірників chroot, просто вкажіть папку chroot, наприклад:

```console
bootlinux /data/manjaro
```

Щоб відмонтувати прив'язану директорію, використовуйте:

```console
killlinux
```

Починаючи з версії v2.1, ви можете завершити певний примірник, просто вкажіть папку chroot, наприклад:

```console
killlinux /data/manjaro
```

Щоб створити образ, використовуйте:

```console
make_image <шлях до зображення> <назва зображення.img> <розмір зображення в МБ>
```

Щоб змонтувати образ, використовуйте:

```console
mount_image <шлях до зображення> <шлях до каталогу Linux>
```

## Доступні дистрибутиви
- Alpine Linux, встановлений в /data/alpine
- Arch Linux, встановлений в /data/arch
- Debian, встановлений в /data/debian
- Fedora, встановлений в /data/fedora
- Kali Linux, встановлений в /data/kali
- Manjaro ARM, встановлений в /data/manjaro
- Ubuntu, встановлений в /data/ubuntu
- Void Linux, встановлений в /data/void

...більше дистрибутивів буде додано незабаром

## Підтримувані архітектури
- arm
- aarch64
- x86
- x64

## ПЛАНИ
- [ ] Перемістити всі файли, що використовуються в lhroot, до мого репозиторію (WIP)
- [ ] Вбудована підтримка аудіо
- [ ] Крос-компіляція всіх залежностей

## Подяки
- [mod-util](https://github.com/veez21/mod-util) від @veez21
- Magisk від @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Ліцензія
Ліцензовано під GNU GPL v3

~~Rootfs tarball взятий з [Репозиторію](https://github.com/EXALAB/Anlinux-Resources) AnLinux~~
Більшість rootfs tarball дистрибутивів були перебудовані та збережені в [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Підтримка
- Відкрийте питання тут
- або відвідайте [Тему на XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Примітка
- Якщо ви хочете зберігати свій chroot у файлі зображення, спочатку створіть файл зображення за допомогою make_image, а потім змонтуйте зображення за допомогою сценарію mount_image.
- coreutils можна встановити за допомогою модуля [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) від @Zackptg5.
- mke2fs можна встановити за допомогою мого [модуля e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), підтримується лише для пристроїв на arm, інші архітектури будуть використовувати applet mke2fs від busybox, буде використовувати файлову систему ext2 і обмеження на розмір зображення 2 ГБ.