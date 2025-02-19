# Práctica 6.2 - Despliegue de una aplicación PHP con Nginx y MySQL usando Docker y docker-compose

## Proceso de dockerización de Nginx+PHP+MySQL
Lo primero es conectarse por ssh a la máquina. <br>
![alt text](images5/image.png) <br>

## Estructura de directorios
Ahora se crea la estructura de directorios creando la carpeta practica6-2 primero y luego con estos comandos. <br>
![alt text](images5/image-1.png) <br>
Deberá quedar así la estructura. <br>
![alt text](images5/image-2.png) <br>

## Creación de un contenedor Nginx
Para crear el contendero primero se modifica el fichero docker-compose.yml tal que así. <br>
![alt text](images5/image-5.png) <br>
Se inicia con docker-compose up -d y se comprueba con docker ps. <br>
![alt text](images5/image-4.png) <br>
Y se comprueba que funciona correctamente escribiendo http://IP:Puerto. <br>
![alt text](images5/image-3.png) <br>

## Creación de un contenedor PHP
Para el contenedor PHP se modifica el index.php como en la imagen. <br>
![alt text](images5/image-6.png) <br>
Luego se modifica el default.conf de la carpeta nginx como en la imagen. <br>
![alt text](images5/image-7.png) <br>
Y se modifica el Dockerfile de la carpeta nginx. <br>
![alt text](images5/image-8.png)
Por último antes de probarlo se vuelve a modificar el docker-compose.yml de nuevo. <br>
![alt text](images5/image-9.png) <br>
Se inicia el contenido. <br>
![alt text](images5/image-10.png) <br>
Se comprueba que funciona. <br>
![alt text](images5/image-11.png) <br>
Se comprueba en el navegador escribiendo http://IP:Puerto. <br>
![alt text](images5/image-13.png) <br>

## Creación de un contenedor para datos
Lo primero es volver a modificar el docker-compose.yml de nuevo. <br>
![alt text](images5/image-14.png) <br>
Se inicia y se comprueba de nuevo antes de crear el contenedor de mysql. <br> 
![alt text](images5/image-15.png) <br>

## Creación de un contenedor MySQL
Lo primero es modificar el dockerfile de la carpeta php. <br>
![alt text](images5/image-16.png) <br>
Se vuelve a modificar el docker-compose.yml. <br>
![alt text](images5/image-17.png) <br>
Se modifica el index.php de nuevo y se inicia el contenedor. <br>
![alt text](images5/image-18.png) <br>

## Verificación de conexión a la base de datos
Se comprueba en el navegador escribiendo http://IP:Puerto. <br>
![alt text](images5/image-20.png) <br>
Para solucionar el error se modifica el index.php añadiendo $user = 'root'; y $password = 'secret';
![alt text](images5/image-22.png) <br>
Se comprueba por última vez en el navegador escribiendo http://IP:Puerto. <br>
![alt text](images5/image-21.png) <br>
