[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | **한국어** | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md) 


# Linux Chroot 설치기

시스템리스 Linux chroot 설치기 및 Linux chroot 부팅 스크립트

## 요구 사항
- Magisk로 Root 권한
- busybox 설치됨
- make_image용 coreutils
- make_image용 mke2fs
- 이 모듈

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## 주의
[이 문제](https://github.com/FerryAr/lhroot/issues/18)와 [이 문제](https://github.com/FerryAr/lhroot/issues/21)와 같은 많은 사례로 인해, chroot 폴더 내의 모든 마운트 포인트가 제거하기 전에 언마운트되어 있는지 확인하십시오. 데이터 손실, 전화기 고장 등에 대해 책임을 지지 않습니다. 제가 작성한 모든 코드는 의도적으로 데이터를 삭제하거나 전화기를 고장 내는 것이 아닙니다. Linux 환경에 익숙한 경우에만 이 모듈을 사용하십시오. 사용은 본인 책임입니다!

## 사용 방법

```console
lhroot
```

그리고 지침에 따라 진행하십시오.

설치 후, Linux Chroot로 부팅하려면 다음 명령어를 사용하십시오:

```console
bootlinux
```

v2.1 버전부터는 2개 이상의 chroot 인스턴스를 실행할 수 있으며, chroot 폴더를 전달하면 됩니다. 예를 들어:

```console
bootlinux /data/manjaro
```

바인드 디렉토리를 언마운트하려면 다음 명령어를 사용하십시오:

```console
killlinux
```

v2.1 버전부터는 특정 인스턴스를 종료할 수 있으며, chroot 폴더를 전달하면 됩니다. 예를 들어:

```console
killlinux /data/manjaro
```

이미지를 생성하려면 다음 명령어를 사용하십시오:

```console
make_image <이미지 경로> <이미지 이름.img> <이미지 크기 (MB)>
```

이미지를 마운트하려면 다음 명령어를 사용하십시오:

```console
mount_image <이미지 경로> <Linux 디렉토리 경로>
```

## 사용 가능한 배포판
- Alpine Linux, /data/alpine에 설치됨
- Arch Linux, /data/arch에 설치됨
- Debian, /data/debian에 설치됨
- Fedora, /data/fedora에 설치됨
- Kali Linux, /data/kali에 설치됨
- Manjaro ARM, /data/manjaro에 설치됨
- Ubuntu, /data/ubuntu에 설치됨
- Void Linux, /data/void에 설치됨

...기타 배포판은 곧 추가될 예정입니다

## 지원되는 아키텍처
- arm
- aarch64
- x86
- x64

## TODO
- [ ] lhroot에서 사용하는 모든 파일을 내 리포지토리로 이전 (WIP)
- [ ] 내장 오디오 지원
- [ ] 모든 종속성 크로스 컴파일

## 감사의 말씀
- [mod-util](https://github.com/veez21/mod-util) by @veez21
- Magisk by @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## 라이센스
GNU GPL v3 라이센스 하에 제공됩니다

~~rootfs tarball은 [AnLinux Resources 리포지토리](https://github.com/EXALAB/Anlinux-Resources)에서 가져왔습니다~~
대부분의 배포판 rootfs tarball은 재구성되어 [lhroot-repo](https://github.com/FerryAr/lhroot-repo)에 저장되었습니다

## 지원
- 여기서 문제를 열어주세요
- 또는 [XDA 스레드](https://forum.xda-developers.com/showthread.php?t=4142803)를 방문하세요

## 참고
- chroot를 이미지 파일에 저장하려면 먼저 make_image를 사용하여 이미지 파일을 생성한 다음 mount_image 스크립트를 사용하여 이미지를 마운트하십시오.
- coreutils는 @Zackptg5의 [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) 모듈을 통해 설치할 수 있습니다.
- mke2fs는 제 [e2fsprogs 모듈](https://github.com/FerryAr/e2fsprogs-arm)을 통해 설치할 수 있습니다. arm 장치만 지원하며, 다른 아키텍처는 busybox의 mke2fs applet을 사용하여 ext2 파일 시스템을 사용하며, 이미지 크기 제한은 2GB입니다.