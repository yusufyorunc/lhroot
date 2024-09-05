[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | **हिंदी** | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | [Português](README-PT.md) | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md)


# Linux Chroot इंस्टॉलर

सिस्टमलेस Linux chroot इंस्टॉलर और Linux chroot बूट स्क्रिप्ट

## आवश्यकताएँ
- Magisk के साथ रूटेड
- busybox स्थापित
- make_image के लिए coreutils
- make_image के लिए mke2fs
- यह मॉड्यूल

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## चेतावनी
[इस समस्या](https://github.com/FerryAr/lhroot/issues/18) और [इस समस्या](https://github.com/FerryAr/lhroot/issues/21) जैसे कई मामलों के कारण, कृपया सुनिश्चित करें कि chroot फ़ोल्डर में सभी माउंट प्वाइंट्स को चroot फ़ोल्डर को हटाने से पहले अनमाउंट किया गया है। डेटा खोने, फोन को ब्रिक करने आदि के लिए मैं जिम्मेदार नहीं हूँ। आप इस रिपॉजिटरी में देख सकते हैं कि मैंने जो भी कोड लिखा है, उसका उद्देश्य आपके डेटा को जानबूझकर हटाना या आपके फोन को ब्रिक करना नहीं है। इस मॉड्यूल का उपयोग करें यदि आप Linux वातावरण से परिचित हैं। DWYOR!

## उपयोग

```console
lhroot
```

और निर्देशों का पालन करें।

इंस्टॉलेशन के बाद, Linux Chroot में बूट करने के लिए:

```console
bootlinux
```

v2.1 के बाद, आप 2 या अधिक chroot इंस्टेंस चला सकते हैं, बस chroot फ़ोल्डर को पास करें, उदाहरण के लिए:

```console
bootlinux /data/manjaro
```

बाइंड डायरेक्टरी को अनमाउंट करने के लिए:

```console
killlinux
```

v2.1 के बाद, आप एक विशिष्ट इंस्टेंस को समाप्त कर सकते हैं, बस chroot फ़ोल्डर को पास करें, उदाहरण के लिए:

```console
killlinux /data/manjaro
```

इमेज बनाने के लिए:

```console
make_image <इमेज का पथ> <इमेज नाम.img> <इमेज का आकार (MB)>
```

इमेज को माउंट करने के लिए:

```console
mount_image <इमेज का पथ> <Linux डायरेक्टरी का पथ>
```

## उपलब्ध डिस्ट्रीब्यूशन
- Alpine Linux, /data/alpine पर स्थापित
- Arch Linux, /data/arch पर स्थापित
- Debian, /data/debian पर स्थापित
- Fedora, /data/fedora पर स्थापित
- Kali Linux, /data/kali पर स्थापित
- Manjaro ARM, /data/manjaro पर स्थापित
- Ubuntu, /data/ubuntu पर स्थापित
- Void Linux, /data/void पर स्थापित

...अन्य डिस्ट्रीब्यूशन जल्द ही जोड़े जाएंगे

## समर्थित आर्किटेक्चर
- arm
- aarch64
- x86
- x64

## TODO
- [ ] lhroot में उपयोग किए गए सभी फाइलों को मेरे रिपॉजिटरी में स्थानांतरित करना (WIP)
- [ ] इनबिल्ट ऑडियो समर्थन
- [ ] सभी निर्भरताओं का क्रॉस-कंपाइल

## श्रेय
- [mod-util](https://github.com/veez21/mod-util) @veez21 द्वारा
- Magisk @topjohnwu द्वारा
- [@yusufyorunc](https://github.com/yusufyorunc)

## लाइसेंस
GNU GPL v3 के तहत लाइसेंस प्राप्त

~~rootfs tarball [AnLinux Resources रिपॉजिटरी](https://github.com/EXALAB/Anlinux-Resources) से लिया गया है~~
ज्यादातर डिस्ट्रीब्यूशन के rootfs tarballs को पुनर्निर्मित किया गया है और [lhroot-repo](https://github.com/FerryAr/lhroot-repo) पर संग्रहीत किया गया है

## समर्थन
- यहाँ मुद्दा खोलें
- या [XDA थ्रेड](https://forum.xda-developers.com/showthread.php?t=4142803) पर जाएं

## नोट
- यदि आप अपने chroot को इमेज फ़ाइल में स्टोर करना चाहते हैं, तो पहले make_image का उपयोग करके इमेज फ़ाइल बनाएं और फिर mount_image स्क्रिप्ट का उपयोग करके इमेज को माउंट करें।
- coreutils को @Zackptg5 के [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) मॉड्यूल के माध्यम से स्थापित किया जा सकता है।
- mke2fs को मेरे [e2fsprogs मॉड्यूल](https://github.com/FerryAr/e2fsprogs-arm) के माध्यम से स्थापित किया जा सकता है, केवल arm डिवाइस के लिए समर्थन; अन्य आर्किटेक्चर busybox के mke2fs एप्लेट का उपयोग करेंगे, ext2 फ़ाइल सिस्टम का उपयोग करेंगे और 2GB इमेज आकार तक सीमित होगा।