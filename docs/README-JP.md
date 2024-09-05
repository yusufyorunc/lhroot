[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | **日本語** | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md) 


# Linux Chroot インストーラー

システムレス Linux chroot インストーラーと Linux chroot 起動スクリプト

## 要件
- Magisk による Root 権限
- busybox インストール済み
- make_image 用の coreutils
- make_image 用の mke2fs
- このモジュール

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## 注意
[こちら](https://github.com/FerryAr/lhroot/issues/18)や[こちら](https://github.com/FerryAr/lhroot/issues/21)のような多くのケースがあるため、chroot フォルダー内のすべてのマウントポイントが削除前にアンマウントされていることを確認してください。データの損失や電話機の破損などについては責任を負いません。私が書いたコードは、意図的にデータを削除したり、電話機を破損させたりするものではありません。このモジュールは、Linux 環境に精通している場合に使用してください。自己責任でご使用ください！

## 使用方法

```console
lhroot
```

そして、指示に従ってください。

インストール後、Linux Chroot を起動するには、次のコマンドを使用します：

```console
bootlinux
```

v2.1 以降は、複数の chroot インスタンスを実行できます。chroot フォルダーを指定してください。例：

```console
bootlinux /data/manjaro
```

バインドディレクトリをアンマウントするには、次のコマンドを使用します：

```console
killlinux
```

v2.1 以降は、特定のインスタンスを終了することができます。chroot フォルダーを指定してください。例：

```console
killlinux /data/manjaro
```

イメージを作成するには、次のコマンドを使用します：

```console
make_image <イメージへのパス> <イメージ名.img> <イメージサイズ (MB)>
```

イメージをマウントするには、次のコマンドを使用します：

```console
mount_image <イメージへのパス> <Linux ディレクトリへのパス>
```

## 利用可能なディストリビューション
- Alpine Linux、/data/alpine にインストール済み
- Arch Linux、/data/arch にインストール済み
- Debian、/data/debian にインストール済み
- Fedora、/data/fedora にインストール済み
- Kali Linux、/data/kali にインストール済み
- Manjaro ARM、/data/manjaro にインストール済み
- Ubuntu、/data/ubuntu にインストール済み
- Void Linux、/data/void にインストール済み

...その他のディストリビューションは近日中に追加される予定です

## サポートされているアーキテクチャ
- arm
- aarch64
- x86
- x64

## TODO
- [ ] lhroot で使用されているすべてのファイルを私のリポジトリに移行する (WIP)
- [ ] 内蔵オーディオサポート
- [ ] すべての依存関係のクロスコンパイル

## 謝辞
- [mod-util](https://github.com/veez21/mod-util) by @veez21
- Magisk by @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## ライセンス
GNU GPL v3 の下でライセンスされています

~~rootfs tarball は [AnLinux Resources のリポジトリ](https://github.com/EXALAB/Anlinux-Resources) から取得されました~~
ほとんどのディストリビューションの rootfs tarball は再構築され、[lhroot-repo](https://github.com/FerryAr/lhroot-repo) に保存されています

## サポート
- ここで問題を開く
- または [XDA スレッド](https://forum.xda-developers.com/showthread.php?t=4142803) を訪問する

## 注
- chroot をイメージファイルに保存したい場合は、まず make_image を使用してイメージファイルを作成し、次に mount_image スクリプトを使用してイメージをマウントしてください。
- coreutils は @Zackptg5 の [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) モジュールを介してインストールできます。
- mke2fs は私の [e2fsprogs モジュール](https://github.com/FerryAr/e2fsprogs-arm) を介してインストールできます。arm デバイスのみサポートされており、他のアーキテクチャは busybox の mke2fs applet を使用し、ext2 ファイルシステムを使用し、イメージサイズの制限は 2GB です。