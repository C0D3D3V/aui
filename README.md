# Simple AUI

This is a simplified Version of [helmuthdu's Archlinux Ultimate Install script](https://github.com/helmuthdu/aui)!
This skripts dosen't have that much options as his scripts! It is easy to use for beginners! You will get a advances Arch System after runing the skripts correctly. It will do no changes to your home directories, so the most programs like zsh are not configured after using these skripts! It is possible to use these skripts on a server!



### Project only accepting patches
This project is actively developed and *will* accept PRs

# Archlinux U Install

Install and configure archlinux has never been easier!

You can try it first with a `virtualbox`

## Prerequisites

- A working internet connection
- Logged in as 'root'

## How to get it
### With git
- Increase cowspace partition: `mount -o remount,size=2G /run/archiso/cowspace`
- Get list of packages and install git: `pacman -Sy git`
- get the script: `git clone git@github.com:C0D3D3V/simpleAui.git`

### Without git
- get the script: ` wget https://github.com/c0d3d3v/simpleAui/tarball/master -O - | tar xz`
    - an alternate URL (for less typing (github shorten)) is ` wget https://git.io/vpphv -O - | tar xz`

## How to use
- Live install [install system base]: `cd <dir> && ./liveinstall`
- Post install [install the rest...]: `cd <dir> && ./postinstall`

## LIVEINSTALL SCRIPT
You can run `cd <dir> && ./relive` if you already installed Arch with the script from [drizzt](https://github.com/drizzt/vps2arch).

Postinstall will install a clean Arch base. No software will be installed. No changes will be done to the system without your agreement! 

- Configure keymap
- Select editor
- Automatic configure mirrorlist [German mirror server are default! In line 46 you can change the country code for the mirror servers!]
- Configure Luks + LVM
- Create partition
- Format partitions
- Install system base [with basic components]
- Configure fstab
- Configure hostname
- Configure timezone [German Timezone is deafult (line 320)]
- Configure hardware clock
- Configure locale [German locals are default (line 331 to 335)]
- Configure mkinitcpio
- Install/Configure bootloader [GRUB 2]
- Configure mirrorlist
- Configure root password

Reboot your system after installation!

## POSTINSTALL SCRIPT
You can run postinstall at anytime again. It will install missing programs and ignore alrady installed programms

It is possible to use this skript on a Server! If you run this skript on a server, the skript will not install any tool with a GUI and only install necessery server tools!
This script will only ask you a few questions at the beginning, after that it runs till it ends!

- Backup all modified files
- Install additional repositories (AUR)
- Create and configure new user
- Install and configure sudo
- Automatic enable services in systemd
- Install an AUR Helper [yaourt]
- Install base system
- Install systemd
- Install Preload
- Install Xorg
- Install GPU Drivers
- Install CUPS
- Install Additional wireless/bluetooth firmwares
- Ensuring access to GIT through a firewall
- Install KDE [Gnome is in progress]
- Install Developement tools [Vim, Emacs, Intellij...]
- Install Office apps [LibreOffice, Latex...]
- Install System tools [Virtualbox, Htop...]
- Install Graphics apps [Inkscape, Gimp...]
- Install Internet apps [Firefox, Jdownloader...]
- Install Multimedia apps [VLC, Codecs...]
- Install Games [Teeworlds...]
- Install Fonts [Liberation, MS-Fonts, Google-webfonts...]
- Many More...

