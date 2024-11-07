# Instalació d'OwnCloud
## Instal·lacio de la versió 7.4 de PHP a Ubnutu 24.04
Per a instal·lar OwnCloud nececesitem la versió 7.4 de PHP.
Les comandes seguents son les necesarries per a actualitzar el PHP.

Amb aquesta comanda instalem els requisits de PPA (arxius de paquets personals)
```bash
sudo apt install software-properties-common -y
```
Instalem les eines necesaries per a poder treballar amb PPA
```bash
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
```
