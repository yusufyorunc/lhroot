[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | **Tiếng Việt** | [Indonesian](README-ID.md)


# Trình cài đặt Linux Chroot

Trình cài đặt Linux chroot không hệ thống và script khởi động Linux chroot

## Yêu cầu
- Đã root với Magisk
- Đã cài đặt busybox
- coreutils cho make_image
- mke2fs cho make_image
- Module này

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## LƯU Ý
Do nhiều trường hợp như [này](https://github.com/FerryAr/lhroot/issues/18) và [này](https://github.com/FerryAr/lhroot/issues/21). Hãy đảm bảo rằng TẤT CẢ các điểm gắn kết trên thư mục chroot đã được UNMOUNT trước khi xóa thư mục chroot. Tôi không chịu trách nhiệm về việc mất dữ liệu, làm hỏng điện thoại, v.v. Bạn có thể kiểm tra kho mã này để biết rằng tất cả các mã tôi đã viết không có ý định xóa dữ liệu của bạn hoặc làm hỏng điện thoại của bạn. Sử dụng module này nếu bạn quen thuộc với môi trường Linux. DWYOR!

## Sử dụng

```console
lhroot
```

và làm theo hướng dẫn

Sau khi cài đặt để khởi động vào Linux Chroot sử dụng:

```console
bootlinux
```

Sau phiên bản v2.1, bạn có thể chạy 2 hoặc nhiều phiên bản chroot, chỉ cần truyền thư mục chroot, ví dụ:

```console
bootlinux /data/manjaro
```

Để unmount thư mục liên kết sử dụng:

```console
killlinux
```

Sau phiên bản v2.1, bạn có thể kết thúc phiên bản cụ thể, chỉ cần truyền thư mục chroot, ví dụ:

```console
killlinux /data/manjaro
```

Để tạo hình ảnh sử dụng:

```console
make_image <đường dẫn tới ảnh> <tên ảnh.img> <kích thước ảnh tính bằng MB>
```

Để gắn kết hình ảnh sử dụng:

```console
mount_image <đường dẫn tới ảnh> <đường dẫn tới thư mục linux>
```

## Các bản phân phối có sẵn
- Alpine Linux, được cài đặt tại /data/alpine
- Arch Linux, được cài đặt tại /data/arch
- Debian, được cài đặt tại /data/debian
- Fedora, được cài đặt tại /data/fedora
- Kali Linux, được cài đặt tại /data/kali
- Manjaro ARM, được cài đặt tại /data/manjaro
- Ubuntu, được cài đặt tại /data/ubuntu
- Void Linux, được cài đặt tại /data/void

...thêm nhiều bản phân phối sẽ sớm được thêm vào

## Kiến trúc được hỗ trợ
- arm
- aarch64
- x86
- x64

## CẦN LÀM
- [ ] Di chuyển tất cả các tệp sử dụng trong lhroot vào kho của tôi (WIP)
- [ ] Hỗ trợ âm thanh tích hợp sẵn
- [ ] Biên dịch chéo tất cả các phụ thuộc

## Ghi nhận
- [mod-util](https://github.com/veez21/mod-util) bởi @veez21
- Magisk bởi @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Giấy phép
Được cấp phép theo GNU GPL v3

~~Rootfs tarball được lấy từ [Repository](https://github.com/EXALAB/Anlinux-Resources) của AnLinux~~
Hầu hết các rootfs tarball của bản phân phối đã được xây dựng lại và lưu trữ tại [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Hỗ trợ
- Mở vấn đề tại đây
- hoặc ghé thăm [XDA Thread](https://forum.xda-developers.com/showthread.php?t=4142803)

## Lưu ý
- Nếu bạn muốn lưu chroot vào file hình ảnh, tạo file hình ảnh trước bằng make_image sau đó gắn kết hình ảnh bằng script mount_image.
- coreutils có thể được cài đặt qua module [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) của @Zackptg5.
- mke2fs có thể được cài đặt qua module [e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm) của tôi, hỗ trợ cho thiết bị arm chỉ, các kiến trúc khác sẽ sử dụng applet mke2fs của busybox, sẽ sử dụng hệ thống tệp ext2 và giới hạn kích thước hình ảnh là 2GB.