[English](README.md) | **العربية** | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# مثبت Linux Chroot

مثبت Chroot لنظام Linux بدون نظام وسكربت إقلاع Chroot لـ Linux

## المتطلبات
- جهاز له صلاحيات الجذر (Root) باستخدام Magisk
- مثبت busybox
- coreutils لـ make_image
- mke2fs لـ make_image
- هذه الوحدة

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## ملاحظة
بسبب العديد من الحالات مثل [هذه](https://github.com/FerryAr/lhroot/issues/18) و [هذه](https://github.com/FerryAr/lhroot/issues/21)، يرجى التأكد من أن جميع نقاط التثبيت في مجلد chroot قد تم إلغاء تثبيتها قبل إزالة مجلد chroot. أنا غير مسؤول عن فقدان البيانات أو تلف الهاتف أو غيرها من المشكلات. يمكنك التحقق من هذا المستودع للتأكد من أن جميع الشيفرات التي كتبتها لا تهدف عمداً إلى حذف بياناتك أو تلف هاتفك. استخدم هذه الوحدة إذا كنت على دراية ببيئة Linux. استخدم على مسؤوليتك الخاصة!

## الاستخدام

```console
lhroot
```

واتبع التعليمات.

بعد التثبيت، لبدء التشغيل في Linux Chroot، استخدم:

```console
bootlinux
```

بعد الإصدار v2.1، يمكنك تشغيل حالتين أو أكثر من chroot، فقط قم بتمرير مجلد chroot، على سبيل المثال:

```console
bootlinux /data/manjaro
```

لفصل الدليل المرتبط، استخدم:

```console
killlinux
```

بعد الإصدار v2.1، يمكنك إنهاء حالة محددة، فقط قم بتمرير مجلد chroot، على سبيل المثال:

```console
killlinux /data/manjaro
```

لإنشاء صورة، استخدم:

```console
make_image <مسار الصورة> <اسم الصورة.img> <حجم الصورة بـ MB>
```

لمونت الصورة، استخدم:

```console
mount_image <مسار الصورة> <مسار دليل Linux>
```

## التوزيعات المتاحة
- Alpine Linux، مثبت في /data/alpine
- Arch Linux، مثبت في /data/arch
- Debian، مثبت في /data/debian
- Fedora، مثبت في /data/fedora
- Kali Linux، مثبت في /data/kali
- Manjaro ARM، مثبت في /data/manjaro
- Ubuntu، مثبت في /data/ubuntu
- Void Linux، مثبت في /data/void

...سيتم إضافة المزيد من التوزيعات قريبًا

## العمارة المدعومة
- arm
- aarch64
- x86
- x64

## TODO
- [ ] ترحيل جميع الملفات المستخدمة في lhroot إلى مستودعي (قيد العمل)
- [ ] دعم الصوت المدمج
- [ ] تجميع جميع التبعيات عبر الأنظمة

## الشكر
- [mod-util](https://github.com/veez21/mod-util) بواسطة @veez21
- Magisk بواسطة @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## الترخيص
مرخص بموجب GNU GPL v3

~~تم الحصول على tarball rootfs من [مستودع AnLinux Resources](https://github.com/EXALAB/Anlinux-Resources)~~
تم إعادة بناء معظم tarballs rootfs للتوزيعات وتخزينها في [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## الدعم
- افتح مشكلة هنا
- أو قم بزيارة [منتدى XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## ملاحظة
- إذا كنت ترغب في تخزين chroot في ملف صورة، قم أولاً بإنشاء ملف الصورة باستخدام make_image ثم قم بتركيب الصورة باستخدام سكربت mount_image.
- يمكن تثبيت coreutils عبر وحدة [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) الخاصة بـ @Zackptg5.
- يمكن تثبيت mke2fs عبر [وحدة e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm)، تدعم فقط أجهزة arm؛ ستستخدم العمارات الأخرى أدوات mke2fs من busybox، وستستخدم نظام الملفات ext2 وتقتصر على حجم صورة يبلغ 2 جيجابايت.