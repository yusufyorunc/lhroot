[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | **Русский** | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md) 


# Установщик Linux Chroot

Установщик системного Linux chroot и скрипт запуска Linux chroot

## Требования
- Root с Magisk
- Установлен busybox
- coreutils для make_image
- mke2fs для make_image
- Этот модуль

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## ВНИМАНИЕ
Из-за множества случаев, как [этот](https://github.com/FerryAr/lhroot/issues/18) и [этот](https://github.com/FerryAr/lhroot/issues/21), убедитесь, что ВСЕ точки монтирования в папке chroot размонтированы перед удалением папки chroot. Я не несу ответственности за потерю данных, повреждение телефона и т. д. Вы можете проверить этот репозиторий, чтобы убедиться, что весь написанный мной код не направлен на удаление ваших данных или повреждение телефона. Используйте этот модуль, если вы знакомы с окружением Linux. Используйте на свой страх и риск!

## Использование

```console
lhroot
```

и следуйте инструкциям.

После установки, чтобы войти в Linux Chroot, используйте:

```console
bootlinux
```

Начиная с версии v2.1, вы можете запускать 2 или более экземпляров chroot, просто укажите папку chroot, например:

```console
bootlinux /data/manjaro
```

Чтобы размонтировать привязанный каталог, используйте:

```console
killlinux
```

Начиная с версии v2.1, вы можете завершить конкретный экземпляр, просто укажите папку chroot, например:

```console
killlinux /data/manjaro
```

Чтобы создать образ, используйте:

```console
make_image <путь к изображению> <имя изображения.img> <размер изображения в МБ>
```

Чтобы смонтировать образ, используйте:

```console
mount_image <путь к изображению> <путь к каталогу linux>
```

## Доступные дистрибутивы
- Alpine Linux, установлен в /data/alpine
- Arch Linux, установлен в /data/arch
- Debian, установлен в /data/debian
- Fedora, установлен в /data/fedora
- Kali Linux, установлен в /data/kali
- Manjaro ARM, установлен в /data/manjaro
- Ubuntu, установлен в /data/ubuntu
- Void Linux, установлен в /data/void

...скоро будет добавлено больше дистрибутивов

## Поддерживаемые архитектуры
- arm
- aarch64
- x86
- x64

## ПЛАНЫ
- [ ] Переместить все файлы, используемые в lhroot, в мой репозиторий (WIP)
- [ ] Встроенная поддержка аудио
- [ ] Кросс-компиляция всех зависимостей

## Благодарности
- [mod-util](https://github.com/veez21/mod-util) от @veez21
- Magisk от @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Лицензия
Лицензировано по GNU GPL v3

~~Архив rootfs взят из [Репозитория](https://github.com/EXALAB/Anlinux-Resources) AnLinux~~
Большинство архивов rootfs дистрибутивов были пересобраны и сохранены в [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Поддержка
- Открыть вопрос здесь
- или посетить [Тему на XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Примечание
- Если вы хотите хранить свой chroot в файле изображения, сначала создайте файл изображения с помощью make_image, затем смонтируйте изображение с помощью скрипта mount_image.
- coreutils можно установить через модуль [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) от @Zackptg5.
- mke2fs можно установить через мой [модуль e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), поддержка только для устройств на arm, другие архитектуры будут использовать applet mke2fs от busybox, будет использовать файловую систему ext2 и ограничение на размер изображения 2 ГБ.