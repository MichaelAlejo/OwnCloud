# Instalació d'OwnCloud
## Instal·lacio de la versió 7.4 de PHP a Ubnutu 24.04
Per a instal·lar OwnCloud nececesitem la versió 7.4 de PHP.
Les comandes seguents son les necesarries per a actualitzar el PHP.

Amb aquesta comanda instalem els requisits de PPA (arxius de paquets personals).
```bash
sudo apt install software-properties-common -y
```
Instalem les eines necesaries per a poder treballar amb PPA.
```bash
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
```
Actualitzem
``` bash
sudo apt update
```
Amb aquestes 3 comandes instalem les llibreries de PHP de la versio 7.4.
``` bash
sudo apt install php7.4 -y
```
``` bash
sudo apt install -y php libapache2-mod-php7.4
```
``` bash
sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl
```
Amb aquesta comanda seleccionem la versio de PHP que necessitem, en aquest cas necesitem la 7.4.
``` bash
sudo update-alternatives --config phpmmm
```
Ara activem els moduls que necesitem d'Apache2 per a que funcioni.
``` bash
sudo a2enmod proxy_fcgi setenvif
```
``` bash
sudo a2enconf php7.4-fpm
```
Y per finalitzar amb l'instalació de la versio 7.4 de PHP, reiniciem l'Apache2.
``` bash
sudo service apache2 restart
```
## Comandes per l'istalacio i configuració de OwnCloud
Per a instalar i configurar OwnCloud, farem us **d'apache2**, al instalar Apache2 es creara una carpeta dins de **/var/www/html**, on treballarem.
## Comandes per l'instalació d'Apache2 i mysql, i llibreries de PHP
Actualitzem la nostra maquina.
``` bash
sudo apt update
```
Aquesta no es obligatoria possar-la, pero es millor, a mes que triga molt en procesar aquesta comanda.
``` bash
sudo apt upgrade
```
Instalem el servidor web **d'Apache2**
``` bash
sudo apt install -y apache2
```
Instalem la base de dades de mysql
``` bash
sudo apt install -y apache2
```
Instalem algunes llibreries **PHP**, que aquest es el lenguatge de totes les aplicacions.
``` bash
sudo apt install -y php libapache2-mod-php
```
``` bash
sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl
```
Y per finalitzar reiniciem el servidor d'Apache2
``` bash
sudo systemctl restart apache2
```
## Configurem la base de dades de mysql
### Entrem a la consola de dades de mysql per posar tots aquestes comandes.
Des d'un terminal on siguem **root** posem aquesta comanda per entrar a la terminal de mysql
``` bash
sudo mysql
```
### Creem una base de dades.
Dins el terminal de mysql creem una base de dades, ja que al estar creant aquesta nova base de dades, li posem el nom de **bbdd**
``` bash
CREATE DATABASE bbdd;
```
### Creacio del nostre usuari
Ara tenim que crear un nou usuari, amb un usuari i una contrasenya, a més que utilitzarem l'IP de **localhost**
``` bash
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
### Per finalitzar li donem privilegis al nostre usuari
``` bash
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
```
### Sortim de la base de dades
``` bash
exit
```
### Ens asegurem de que hem fet tots els passos bé.
Amb el terminal normal sense privilegis provem a conectarnos a mysql i introduem la nostra contrasenya de mysql.
``` bash
mysql -u usuario -p
```
## Descarguem l'apliccacio web
Descarguem el .zip de la nostra cloud, en aquest cas la de OwnCloud:
https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip





