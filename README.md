
# Install Rasbperry pi os
## Installer imager
Install the raspberry pi imager
### Debian (ubuntu)
```sh
sudo apt update
sudo apt upgrade
sudo apt install rpi-imager
```

### other
last ned via https://www.raspberrypi.com/software/


## Installer Rasbperry pi os 
### Installer os-et på ett sd-kort
- Plugg inn sd/usb en din
kjør rpi-imager
Linux:
```sh
rpi-imager
```
1. Under **CHOOSE DEVICE** velg **Raspberry Pi 4**
2. Under **CHOOSE OS** velg **Raspberry Pi OS (other)** -> **Raspberry Pi OS Lite (64-bit)**
3. Under **CHOOSE STORAGE** velg SD-kortet du har lyst til å installere os-et på.
> [!danger]
> Dette sletter alle dataene fra kortet ditt

4. Trykk **NEXT**
5. Trykk **EDIT SETTINGS**
### OS customization
1. Sett hostnamet ditt. Husk dette til senere
> [!info]
> Senere når jeg skriver `<hostname>` bytt det ut med dette hostnamet
2. Sett brukernavn og passord
> [!info]
> Senere når jeg skriver `<username>` bytt det ut med dette brukernavnet

> [!info]
> Husk passordet. Om du glemmer det er det vanskelig å få tilbake OS (med mindre du har satt opp SSH-nøkler)

3. Trykk **Set locale settings** (checkboxen til venstre)
Om du bruker annet annet keyboard layout sett det her
> [!info]
> Norskt layout er no

