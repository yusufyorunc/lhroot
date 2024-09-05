[English](README.md) | [العربية](README-AR.md) | [Deutsch](README-DE.md) | [Español](README-ES.md) | [Français](README-FR.md) | [हिंदी](README-IN.md) | [Italiano](README-IT.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Polski](README-PL.md) | **Português** | [Русский](README-RU.md) | [Українська](README-UA.md) | [Türkçe](README-TR.md) | [简体中文](README-CN.md) | [Tiếng Việt](README-VI.md) | [Indonesian](README-ID.md) 


# Instalador do Linux Chroot

Instalador de Linux chroot sem sistema e script de inicialização do Linux chroot

## Requisitos
- Root com Magisk
- busybox instalado
- coreutils para make_image
- mke2fs para make_image
- Este módulo

![Manjaro-Linux-Android](https://i.ibb.co/gdpw8QG/lhroot.png)

## AVISO
Devido a muitos casos como [este](https://github.com/FerryAr/lhroot/issues/18) e [este](https://github.com/FerryAr/lhroot/issues/21), certifique-se de que TODOS os pontos de montagem na pasta chroot estejam DESMONTADOS antes de remover a pasta chroot. Não me responsabilizo por perda de dados, danos ao telefone, etc. Você pode verificar neste repositório que todo o código que escrevi não visa intencionalmente remover seus dados ou danificar seu telefone. Use este módulo se você estiver familiarizado com o ambiente Linux. Use por sua conta e risco!

## Uso

```console
lhroot
```

e siga as instruções.

Após a instalação, para iniciar no Linux Chroot, use:

```console
bootlinux
```

A partir da versão v2.1, você pode executar 2 ou mais instâncias de chroot, basta passar a pasta chroot, por exemplo:

```console
bootlinux /data/manjaro
```

Para desmontar o diretório vinculado, use:

```console
killlinux
```

A partir da versão v2.1, você pode encerrar uma instância específica, basta passar a pasta chroot, por exemplo:

```console
killlinux /data/manjaro
```

Para criar uma imagem, use:

```console
make_image <caminho para a imagem> <nome_da_imagem.img> <tamanho da imagem em MB>
```

Para montar a imagem, use:

```console
mount_image <caminho para a imagem> <caminho para o diretório Linux>
```

## Distribuições Disponíveis
- Alpine Linux, instalado em /data/alpine
- Arch Linux, instalado em /data/arch
- Debian, instalado em /data/debian
- Fedora, instalado em /data/fedora
- Kali Linux, instalado em /data/kali
- Manjaro ARM, instalado em /data/manjaro
- Ubuntu, instalado em /data/ubuntu
- Void Linux, instalado em /data/void

...mais distribuições serão adicionadas em breve

## Arquiteturas Suportadas
- arm
- aarch64
- x86
- x64

## A FAZER
- [ ] Migrar todos os arquivos usados no lhroot para meu repositório (WIP)
- [ ] Suporte de Áudio embutido
- [ ] Cross-compilar todas as dependências

## Créditos
- [mod-util](https://github.com/veez21/mod-util) por @veez21
- Magisk por @topjohnwu
- [@yusufyorunc](https://github.com/yusufyorunc)

## Licença
Licenciado sob GNU GPL v3

~~O arquivo rootfs foi retirado do [Repositório](https://github.com/EXALAB/Anlinux-Resources) do AnLinux~~
A maioria dos arquivos rootfs das distribuições foram reconstruídos e armazenados no [lhroot-repo](https://github.com/FerryAr/lhroot-repo)

## Suporte
- Abra um problema aqui
- ou visite o [Tópico no XDA](https://forum.xda-developers.com/showthread.php?t=4142803)

## Nota
- Se você deseja armazenar seu chroot em um arquivo de imagem, crie o arquivo de imagem primeiro usando make_image e depois monte a imagem usando o script mount_image.
- coreutils pode ser instalado através do módulo [ccbins](https://github.com/Magisk-Modules-Repo/ccbins) do @Zackptg5.
- mke2fs pode ser instalado através do meu [módulo e2fsprogs](https://github.com/FerryAr/e2fsprogs-arm), suporte apenas para dispositivos arm; outras arquiteturas usarão o applet mke2fs do busybox, que usará o sistema de arquivos ext2 e terá o limite de tamanho de imagem de 2GB.