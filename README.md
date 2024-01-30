# Instalacion Lamp  en un ubuntu creado en EC2  
## 1.Instalacion de PHP y Apache2
Actualización repositorios: apt update
## 2.Instalación Apache2:
apt install apache2 -y
## 3.Instalación PHP
apt install php libapache2-mod-php php-mysql -y
## 4.Editamos sitio web por defecto (000-default.conf):
El sitio web (host virtual) quedaría de la siguiente manera:
<VirtualHost *:80>
ServerName www.example.com
ServerAdmin webmaster@localhost
DocumentRoot /var/www/html
DirectoryIndex index.html index.php (Nota: Se debe añadir
esta línea)
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
## 5: Reiniciamos servicio apache2
systemctl restart apache2
