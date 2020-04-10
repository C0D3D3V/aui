# Simple AUI

## Warnung! Aktuell ist nur das `liveinstall`-Skript aktuell. Die Post-Installation werde ich demnächst wieder aktualisieren.

Dieses Skript automatisiert weitestgehend die Installation von Arch-Linux, welche in [meinem anderen Repo](https://github.com/C0D3D3V/arch) beschrieben wird. Es ist eine stark abgeänderte Version von [helmuthdu's Archlinux ulitimativem Installations-Skript](https://github.com/helmuthdu/aui).




### Ich freue mich über jeden der zu diesem Projekt etwas beitragen möchte
An diesem Projekt wird noch aktiv gearbeitet und es werden PRs akzeptiert.


# Motto

Die Installation und Konfiguration von Arch-Linux war nie einfacher! :D 
Natürlich gibt es noch unzählige andere Varianten Arch-Linux zu installieren, beispielsweise in dem man strickt dem [Installation guide](https://wiki.archlinux.org/index.php/installation_guide) folgt. Aber wer das öfter als ein mal gemacht hat, weiß dass dies öde wird.

Ich empfehle diese Skripte erst in Virtualbox zu testen, um sich damit vertraut zu machen.


## Erste-Schritte (Vorraussetzung)

Die Skripte müssen auf das [Live-System](https://www.archlinux.de/download) gebracht werden. Entweder über ein extra USB-Stick oder durch das Herunterladen des Repositories.

* Um ein [USB-Stick einzubinden](https://wiki.archlinux.org/index.php/USB_storage_devices) muss mit `lsblk` der Pfad des USB-Sticks ermittelt werden. Anschließend kann dieser in ein erstellten Ordner eingebunden werden.

    lsblk
    mkdir usb
    mount /dev/sdb1 usb
    cd usb/simpleAui

* Alternativ kann das Skript mit `git` heruntergeladen werden. Dazu muss zunächst eine Internetverbindung hergestellt werden. Wenn nur [LAN](https://de.wikipedia.org/wiki/Local_Area_Network) verfügbar ist dann reicht das ausführen von `dhcpcd`, wenn jedoch eine Verbindung mit einem [WLAN](https://de.wikipedia.org/wiki/Wireless_Local_Area_Network) hergestellt werden muss, dann muss `wifi-menu` gestartet werden.

    dhcpcd
    pacman -Sy git
    git clone https://github.com/c0d3d3v/simpleAui
    cd simpleAui


## Wie diese Skripte verwendet werden 

Um die absolute **Basis** des Arch-Linux Betriebsystems zu installieren reicht das Ausführen des `liveinstall`-Skripts im Live-System. Das Skript führt dich durch eine Auswahl von Optionen, bleib wachsam während des gesamten Prozesses. Fehler sind hier kritisch aber können gegebenfalls behoben werden. Das Skript frägt bei kritischen Schritten ob diese erfolgreich waren.

    ./liveinstall

Um die Installation abzuschließen mit [meiner Liste an empfohlenen Programmen](https://github.com/C0D3D3V/arch/packages) muss nach dem Ausführen des `liveinstall`-Skript auch das `postinstall`-Skript ausgeführt werden. Dieses wird als Admin entweder in der [arch-chroot](https://wiki.archlinux.org/index.php/Chroot) Umgebung ausgeführt (Das Dateisystem ist nach dem `liveinstall`-Skript noch unter `/mnt/` eingebunden) oder im neu installierten Betriebsystem (dazu die ersten Schritte wiederholen).

    ./postinstall

## Was macht das `liveinstall` Skript?

Die Schritte des Skriptes sind unter [https://github.com/C0D3D3V/arch/blob/master/install_arch.md](https://github.com/C0D3D3V/arch/blob/master/install_arch.md) dokumentiert.


## Was macht das `postinstall` Skript?

Weil das Skript noch nicht abgeändert wurde lass ich noch den alten Text dazu hier:

You can run postinstall at anytime again. It will install missing programs and ignore alrady installed programms

It is possible to use this skript on a Server! If you run this skript on a server, the skript will not install any tool with a GUI and only install necessery server tools!
This script will only ask you a few questions at the beginning, after that it runs till it ends!

- Backup all modified files
- Install additional repositories (AUR)
- Create and configure new user
- Install and configure sudo
- Automatic enable services in systemd
- Install an AUR Helper [yay]
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

