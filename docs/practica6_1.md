# Práctica 6.1 - Dockerización del despliegue de una aplicación Node.js

## Despliegue con Docker
Lo primero es conectarse por ssh a la máquina virtual. <br>
![alt text](images4/image-66.png) <br>
Se clona el repositorio de la imagen con git clone. <br>
![alt text](images4/image-67.png) <br>
Se instala docker con el comando de la imagen. <br>
![alt text](images4/image-68.png) <br>
Se modifica el dockerfile del repositorio para que quede como en la imagen para poder construir la imagen y correr el contenedor. <br>
![alt text](images4/image-69.png) <br>
Y se procede a hacer build de la imagen con el siguiente comando poniendole el nombre de librodirecciones. <br>
![alt text](images4/image-70.png) <br>
Se le asigna el puerto 3000 con el siguiente comando. <br>
![alt text](images4/image-71.png) <br>
Y se buscamos en el explorador, todavía no sale nada. <br>
![alt text](images4/image-72.png) <br>

## Docker Compose
Lo primero es instalar docker compose si no se tiene. La versión de la imagen es válida. <br>
![alt text](images4/image-73.png) <br>
Se crea un fichero .yml con la siguiente estructura para describir la aplicación. <br>
![alt text](images4/image-74.png) <br>
Se ejecuta lo creado con el comando de debajo para ejecutar las tablas. <br>
![alt text](images4/image-75.png) <br>
Se construye los contenedores con el siguiente comando. <br>
![alt text](images4/image-76.png) <br>
Por último se corren los test para verificar el correcto funcionamiento.<br>
![alt text](images4/image-77.png) <br> 
![alt text](images4/image-78.png) <br>

## Tarea
Para probar que funciona correctamente la base de datos lo primero es añadir un usuario como el del ejemplo con dicha sentencia. <br>
![alt text](images4/image-79.png) <br>
Se comprueba los usuarios de la base de datos en general primero y luego el que tiene id 1.<br>
![alt text](images4/image-80.png) <br>
Por último se elimina el usuario creado y se muestra que se han eliminado todos. <br>
![alt text](images4/image-81.png) <br>