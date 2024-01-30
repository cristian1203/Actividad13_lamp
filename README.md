# Instalacion Lamp  en un ubuntu creado en EC2  
## 1.Instalacion de PHP y Apache2
Actualización repositorios: apt update  
![image](https://github.com/cristian1203/Actividad13_lamp/assets/151034282/43bc1f56-b522-4cb9-9802-d0fa766c4e7c)
## 2.Instalación Apache2:
apt install apache2 -y  
![image](https://github.com/cristian1203/Actividad13_lamp/assets/151034282/a490cb2c-8d4b-40af-94c2-d0a2e1920213)
## 3.Instalación PHP
apt install php libapache2-mod-php php-mysql -y  
![image](https://github.com/cristian1203/Actividad13_lamp/assets/151034282/e3ea6d15-e908-4f4b-872d-7f97321152cb)
## 4.Editamos sitio web por defecto (000-default.conf) en la ruta  /etc/apache2:
El sitio web (host virtual) quedaría de la siguiente manera:  
<VirtualHost *:80>  
ServerName www.example.com  
ServerAdmin webmaster@localhost  
DocumentRoot /var/www/html  
DirectoryIndex index.html index.php (Nota: Se debe añadir esta línea)  
ErrorLog ${APACHE_LOG_DIR}/error.log  
CustomLog ${APACHE_LOG_DIR}/access.log combined  
</VirtualHost>  
![image](https://github.com/cristian1203/Actividad13_lamp/assets/151034282/d72e2df0-824e-4e3f-ac9f-a57d9a4ac732)
## 5: Reiniciamos servicio apache2
systemctl restart apache2  
![image](https://github.com/cristian1203/Actividad13_lamp/assets/151034282/6438c0e8-e37b-4d7e-91ea-b9836d751b90)
## 6.Comprobación de LAMP  
Creamos en el “documentroot” del sitio web por defecto
(/var/www/html) una página de prueba:<html>  
(<head>
    <title>Actividad 1.3.1</title>  
    
</head>  
<body>  
    <?php echo "<h1>Actividad 1.3.1: LAMP Sever. Autor: Tu nombre y apellidos</h1>"; ?>     
</body>  
</html> )
Desde el navegador e incluimos la siguiente URL:
http://ip_servidor/info.php  
![image](https://github.com/cristian1203/Actividad13_lamp/assets/151034282/9375a8aa-89dc-47fb-8cd9-822ddd42dee7)



