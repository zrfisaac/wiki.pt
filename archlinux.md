<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.archlinux : 0.0.1 -->

<!-- # [ markdown ] -->
# Arch Linux

## Descrição
Arch Linux é uma distribuição leve e de lançamento contínuo para usuários avançados, oferecendo personalização completa e as atualizações mais recentes. Possui Pacman e AUR para amplo suporte de software.

---

## Índice
- Padrão
  - dd : `dd bs=4M if=/zrfisaac/repository/os/archlinux/archlinux-amd64.iso of=/dev/sda conv=fsync oflag=direct status=progress`
  - /etc/default/grub : `cryptdevice=UUID=7b927af8-fd64-4dcc-9c4e-a9819b6d150c:ZRFISAAC`
  - /etc/mkinitcpio.conf : `HOOKS=(base udev autodetect microcode modconf kms keyboard keymap consolefont block ` **encrypt** ` filesystems fsck)`
- [Shell](#shell)
  - [Mídia de instalação flash USB](#mídia-de-instalação-flash-usb)

---

## [Shell](#índice)

### [Mídia de instalação flash USB](#índice)

- usando `cat` :
```bash
cat /zrfisaac/repository/os/archlinux/archlinux-amd64.iso > /dev/sda
```

- usando `cp` :
```bash
cp /zrfisaac/repository/os/archlinux/archlinux-amd64.iso /dev/sda
```

- usando `dd` :
```bash
dd bs=4M if=/zrfisaac/repository/os/archlinux/archlinux-amd64.iso of=/dev/sda conv=fsync oflag=direct status=progress
```

- usando `tee` :
```bash
tee < /zrfisaac/repository/os/archlinux/archlinux-amd64.iso > /dev/sda
```

- usando `pv` :
```bash
pv /zrfisaac/repository/os/archlinux/archlinux-amd64.iso -Yo /dev/sda
```
