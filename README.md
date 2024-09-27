
# Install Ubuntu
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


## Installer Ubuntu
### Installer os-et på ett sd-kort
- Plugg inn sd/usb en din
kjør rpi-imager
Linux:
```sh
sudo -E rpi-imager
```
1. Under **CHOOSE DEVICE** velg **Raspberry Pi 4**
2. Under **CHOOSE OS** velg **Other general-purpose OS** -> **Ubuntu** -> **Ubuntu Server <version> LTS (64-bit)** 
> <version> kan være hva som hest siden LTS betyr Latest stable
3. Under **CHOOSE STORAGE** velg SD-kortet du har lyst til å installere os-et på.
> [!danger]
> Dette sletter alle dataene fra kortet ditt

4. Trykk **NEXT**
5. Trykk **EDIT SETTINGS**
### OS customization
1. Sett hostnamet ditt. Husk dette til senere
> [!note]
> Senere når jeg skriver `<hostname>` bytt det ut med dette hostnamet
2. Sett brukernavn og passord
> [!note]
> Senere når jeg skriver `<username>` bytt det ut med dette brukernavnet

3. Trykk **Set locale settings** (checkboxen til venstre)
4. Øverst trykk **SERVICES**
5. Trykk **Enable SSH** -> **Allow public-key authentication only**
6. Put publickeyen din her
> [!note]
> denne kan du finne i `~/.ssh/id_ed25519.pub`
7. Trykk **SAVE** 
8. Trykk **YES**
> [!danger]
> Dette er siste øyeblikk til å lagre dataene dine
9. Trykk **YES**
Det kan ta litt tid å installere OS-et
Når den er ferdig ta ut SD-kortet
### Setup på pi-en
1. Putt SD-kortet inn i rpi-en.
> [!Note]
> SD-kort leseren er på motsatt side av ethernet-kabelen
2. Kobl til ethernet på rpi-en
> [!note]
> PC-en din må være på samme nettverk som rpi-en
3. Skru på maskinen
4. ssh-til maskinen
```bash
ssh <username>@<hostname>
```
#### Oppdatere packages
```bash
sudo apt update
sudo apt upgrade
```
#### Sett opp en github ssh-nøkkel
```bash
ssh-keygen
eval "$(ssh-agent -s)"
ssh-add
```
#### Legge til nøkkelen på github
[gå til github](https://github.com/settings/keys)
1. Trykk **New SSH key**
2. Lag en tittel(navn) for nøkkelen
3. kopier linjen fra ~/.ssh/id_ed25519.pub til **Key**
4. Trykk **Add SSH key**

#### Set up static IP
```bash
```
#### Set up all other dependecies
```bash
cd /tmp
git clone git@github.com:Andyson007/raspi-setup.git
cd raspi-setup
chmod +x ./setup
./setup
