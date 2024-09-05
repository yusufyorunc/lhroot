[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | **Español** | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Instalador Linux Chroot

Instalador de Linux chroot sin sistema y script de arranque chroot Linux

## Requisitos
- Root con Magisk
- busybox instalado
- coreutils para make_image
- mke2fs para make_image
- Este módulo

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## AVISO
Debido a muchos casos como [este](https://github.com/FerryAr/lhroot/issues/18) y [este](https://github.com/FerryAr/lhroot/issues/21), asegúrate de que TODOS los puntos de montaje en la carpeta chroot estén DESMONTADOS antes de eliminar la carpeta chroot. No me hago responsable de la pérdida de datos, daños al teléfono, etc. Puedes verificar en este repositorio que todo el código que he escrito no tiene la intención de eliminar tus datos o dañar tu teléfono. Usa este módulo si estás familiarizado con el entorno Linux. ¡Usa bajo tu propio riesgo!

## Uso

```console
lhroot
```

y sigue las instrucciones.

Después de la instalación, para arrancar en Linux Chroot, utiliza:

```console
bootlinux
```

Después de la versión v2.1, puedes ejecutar 2 o más instancias de chroot, simplemente pasa la carpeta chroot, por ejemplo:

```console
bootlinux /data/manjaro
```

Para desmontar el directorio vinculado, usa:

```console
killlinux
```

Después de la versión v2.1, puedes finalizar una instancia específica, simplemente pasa la carpeta chroot, por ejemplo:

```console
killlinux /data/manjaro
```

Para crear una imagen usa:

```console
make_image <ruta a img> <nombre_img.img> <tamaño img en MB>
```

Para montar una imagen usa:

```console
mount_image <ruta a img> <ruta al directorio Linux>
```

## Distribuciones Disponibles
- Alpine Linux, instalado en /data/alpine
- Arch Linux, instalado en /data/arch
- Debian, instalado en /data/debian
- Fedora, instalado en /data/fedora
- Kali Linux, instalado en /data/kali
- Manjaro ARM, instalado en /data/manjaro
- Ubuntu, instalado en /data/ubuntu
- Void Linux, instalado en /data/void

...más distribuciones se agregarán pronto

## Arquitecturas Soportadas
- arm
- aarch64
- x86
- x64

## POR HACER
- [ ] Migrar todos los archivos utilizados en lhroot a mi repositorio (WIP)
- [ ] Soporte de audio integrado
- [ ] Compilación cruzada de todas las dependencias

## Créditos
- [mod-util](https://github.com/veez21/mod-util) por @veez21
- Magisk por @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Licencia
Licenciado bajo GNU GPL v3

~~El tarball rootfs se toma del [Repositorio de AnLinux Resources](https://github.com/EXALAB/Anlinux-Resources)~~
La mayoría de los tarballs rootfs de distribuciones han sido reconstruidos y almacenados en [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Soporte
- Abre un problema aquí
- o visita [el hilo de XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Nota
- Si deseas almacenar tu chroot en un archivo de imagen, primero crea el archivo de imagen usando make_image y luego monta la imagen usando el script mount_image.
- coreutils se puede instalar a través del módulo [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) de @Zackptg5.
- mke2fs se puede instalar a través de mi [módulo e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), solo soporte para dispositivos arm; otras arquitecturas usarán applets mke2fs de busybox, usarán el sistema de archivos ext2 y estarán limitadas a un tamaño de imagen de 2GB.