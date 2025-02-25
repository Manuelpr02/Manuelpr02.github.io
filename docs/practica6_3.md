# Práctica 6.3 - Despliegue de servidores web con usuarios autenticados mediante LDAP usando Docker y docker-compose

## Despliegue con Docker de NGINX + demonio de autenticación LDAP + OpenLDAP
Lo primero es conectarse por ssh a la máquina. <br>
![alt text](images5/image-23.png) <br>
Luego se crea la carpeta Practica6.3 con la siguiente estructura. <br>
![alt text](images5/image-24.png) <br>
Se rellena el index.html para que muestre un hola mundo y el archivo ldap_nginx.conf se rellena con el siguiente contenido. <br>
![alt text](images5/image-25.png) <br>
Por último el docker-compose para poder levantar los contenedores. <br>
![alt text](images5/image-30.png) <br>
Se levanta y se comprueba su funcionamiento. <br>
![alt text](images5/image-27.png) <br>
![alt text](images5/image-29.png) <br>
Por último se comprueba en el explorador escribiendo http://IP:8082. Se registra con los credenciales de antes y ya estaría. <br>
![alt text](images5/image-28.png) <br>

## Despliegue con Docker de PHP + Apache con autenticación LDAP
Se rellena ahora el archivo index.php con el siguiente contenido. <br>
![alt text](images5/image-26.png) <br>
Se rellena el Dockerfile de la carpeta Docker. <br>
![alt text](images5/image-31.png) <br>
Se rellena el archivo ldap_demo.conf de la carpeta Docker. <br>
![alt text](images5/image-32.png) <br>
Se crea un fichero .htaccess para que pida la autentificación. <br>
![alt text](images5/image-33.png) <br>
Se construye ka imagen con el contenido del fichero. <br>
![alt text](images5/image-34.png) <br>
Se levanta el contenedor con el siguiente comando. <br>
![alt text](images5/image-35.png) <br>
Por último se comprueba su funcionamiento escribiendo http://IP:3000/demo y después de autentificarse ya estaría terminado. <br>
![alt text](images5/image-36.png) <br>