# AUI

## Warnung! Aktuell ist nur das `liveinstall`-Skript aktuell. Die Post-Installation werden wir demnächst wieder aktualisieren.

Dieses Skript automatisiert weitestgehend die Installation von Arch-Linux, welche in [einem anderen Repository](https://github.com/C0D3D3V/arch) beschrieben wird. Es ist eine stark abgeänderte Version von [helmuthdu's Archlinux ulitimativem Installations-Skript](https://github.com/helmuthdu/aui).



### Ich freue mich über jeden der zu diesem Projekt etwas beitragen möchte
An diesem Projekt wird noch aktiv gearbeitet und es werden PRs akzeptiert.

Dieses Projekt entsteht in Zusammenarbeit mit [marzzzello](https://github.com/marzzzello) und [mir](https://github.com/C0D3D3V).


## Motto

Die Installation und Konfiguration von Arch-Linux war nie einfacher! :D 
Natürlich gibt es noch unzählige andere Varianten Arch-Linux zu installieren, beispielsweise in dem man strickt dem [Installation guide](https://wiki.archlinux.org/index.php/installation_guide) folgt. Aber wer das öfter als ein mal gemacht hat, weiß dass dies öde wird.

Ich empfehle diese Skripte erst in Virtualbox zu testen, um sich damit vertraut zu machen.

# Einsetzung 

## Erste-Schritte (Vorraussetzung)

Die Skripte müssen auf das [Live-System](https://www.archlinux.de/download) gebracht werden. Entweder durch das Herunterladen des Repositories oder über ein extra USB-Stick.

* Zum Herunterladen muss zunächst eine Internetverbindung hergestellt werden. Wenn nur [LAN](https://de.wikipedia.org/wiki/Local_Area_Network) verfügbar ist dann reicht das ausführen von `dhcpcd`, wenn jedoch eine Verbindung mit einem [WLAN](https://de.wikipedia.org/wiki/Wireless_Local_Area_Network) hergestellt werden muss, dann muss `nmtui` gestartet werden.
```
nmtui
curl -LO git.io/Aui
bash Aui
```

* Um ein [USB-Stick einzubinden](https://wiki.archlinux.org/index.php/USB_storage_devices) muss mit `lsblk` der Pfad des USB-Sticks ermittelt werden. Anschließend kann dieser in ein erstellten Ordner eingebunden werden.

```
lsblk
mkdir usb
mount /dev/sdb1 usb
cd usb/aui
```

## Wie diese Skripte verwendet werden 

Um die absolute **Basis** des Arch-Linux Betriebsystems zu installieren reicht das Ausführen des `setup`-Skripts im Live-System. Das Skript führt dich durch eine Auswahl von Optionen, bleib wachsam während des gesamten Prozesses. Fehler sind hier kritisch aber können gegebenfalls behoben 
werden. Das Skript frägt bei kritischen Schritten ob diese erfolgreich waren.

```
./setup
```

Um die Installation abzuschließen mit [meiner Liste an empfohlenen Programmen](https://github.com/C0D3D3V/arch/packages) muss nach dem Ausführen des `liveinstall`-Skript auch das `postinstall`-Skript ausgeführt werden. Dieses wird als Nutzer mit sudo im neu installierten Betriebsystem ausgeführt.

```
./postinstall
```

## Was macht das `liveinstall` Skript?

Die Schritte des Skriptes sind unter [https://github.com/C0D3D3V/arch/blob/master/install_arch.md](https://github.com/C0D3D3V/arch/blob/master/install_arch.md) dokumentiert.


## Was macht das `postinstall` Skript?

Das Skript führt die *post-Installations*-Schritte aus die in der [Dokumentation](https://github.com/C0D3D3V/arch/tree/master/post_install) beschrieben sind. Des weiteren werden alle [hier beschriebenen Pakete](https://github.com/C0D3D3V/arch/tree/master/packages) installiert.
