[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | **简体中文** | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Linux Chroot 安装器

无系统 Linux chroot 安装器和 Linux chroot 启动脚本

## 要求
- 使用 Magisk 获取 root 权限
- 安装了 busybox
- 用于 make_image 的 coreutils
- 用于 make_image 的 mke2fs
- 此模块

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## 注意
由于许多类似于 [这个](https://github.com/FerryAr/lhroot/issues/18) 和 [这个](https://github.com/FerryAr/lhroot/issues/21) 的情况，请确保在删除 chroot 文件夹之前，所有 chroot 文件夹中的挂载点都已卸载。我不对数据丢失、手机砖化等问题负责。您可以检查这个仓库，确保我编写的所有代码并不故意删除您的数据或使您的手机变砖。请在熟悉 Linux 环境的情况下使用此模块。自行承担风险！

## 使用方法

```console
lhroot
```

并按照说明进行操作。

安装后，要启动 Linux Chroot，请使用：

```console
bootlinux
```

在 v2.1 之后，您可以运行两个或多个 chroot 实例，只需传递 chroot 文件夹，例如：

```console
bootlinux /data/manjaro
```

要卸载绑定目录，请使用：

```console
killlinux
```

在 v2.1 之后，您可以终止特定实例，只需传递 chroot 文件夹，例如：

```console
killlinux /data/manjaro
```

要创建镜像，请使用：

```console
make_image <镜像路径> <镜像名称.img> <镜像大小 MB>
```

要挂载镜像，请使用：

```console
mount_image <镜像路径> <Linux 目录路径>
```

## 可用的发行版
- Alpine Linux，安装在 /data/alpine
- Arch Linux，安装在 /data/arch
- Debian，安装在 /data/debian
- Fedora，安装在 /data/fedora
- Kali Linux，安装在 /data/kali
- Manjaro ARM，安装在 /data/manjaro
- Ubuntu，安装在 /data/ubuntu
- Void Linux，安装在 /data/void

...更多发行版将很快添加

## 支持的架构
- arm
- aarch64
- x86
- x64

## TODO
- [ ] 将 lhroot 中使用的所有文件迁移到我的仓库（进行中）
- [ ] 内置音频支持
- [ ] 交叉编译所有依赖项

## 致谢
- [mod-util](https://github.com/veez21/mod-util) 由 @veez21 提供
- Magisk 由 @topjohnwu 提供
- [@yusufyorunc](https://github.com/yusufyorunc)

## 许可证
依据 GNU GPL v3 许可证

~~rootfs tarball 来源于 [AnLinux Resources Repository](https://github.com/EXALAB/Anlinux-Resources)~~
大多数发行版的 rootfs tarballs 已被重建并存储在 [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## 支持
- 在此处打开问题
- 或访问 [XDA 论坛](https://forum.xda-developers.com/showthread.php?t=4142803)

## 注意事项
- 如果您想将 chroot 存储在镜像文件中，请首先使用 make_image 创建镜像文件，然后使用 mount_image 脚本挂载镜像。
- coreutils 可以通过 @Zackptg5 的 [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) 模块安装。
- mke2fs 可以通过我的 [e2fsprogs 模块](https://github.com/FerryAr/e2fsprogs-arm) 安装，仅支持 arm 设备；其他架构将使用 busybox 的 mke2fs 工具，使用 ext2 文件系统，并限制图像大小为 2GB。