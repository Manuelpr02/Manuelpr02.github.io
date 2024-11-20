# Práctica 3.4: Despliegue de una aplicación una aplicación React en Netlify (PaaS)

## Creación de nuestra aplicación
Lo primero es crear los siguientes archivos en un mismo directorio para crear la aplicación: <br>
![alt text](images3/image-30.png)
![alt text](images3/image-31.png)
![alt text](images3/image-32.png)
Ahora se crea el package.json con npm init. <br>
![alt text](images3/image-33.png)
Y se comprueba qque funciona ejecutando node aplicacion.js y comprobándolo con la ip de la máquina y el puerto que por defecto es el 8080. <br>
![alt text](images3/image-34.png)
![alt text](images3/image-35.png)

## Aplicación para Netlify
Se clona el repositorio con el siguiente comando: git clone https://github.com/StackAbuse/color-shades-generator <br>
Lo primero es registrarse en NETLIFY con el correo y sin usar el Github. <br>
![alt text](images3/image-36.png)
Luego se crea un token de acceso y se copia dicho token. <br>
![alt text](images3/image-39.png)
![alt text](images3/image-40.png)
![alt text](images3/image-41.png)

## Despliegue mediante CLI
Se instala el CLI de NETLIFY. <br>
![alt text](images3/image-37.png)
Se guarda el token de antes para acceder. <br>
![alt text](images3/image-42.png)
Se hace el login con el comando siguiente: <br>
![alt text](images3/image-43.png)
Dentro del proyecto se instala las librerías. <br>
![alt text](images3/image-44.png)
Se ejecuta el proyecto. <br>
![alt text](images3/image-45.png)
Se hace un pre despliegue ahora con netlify deploy. <br>
![alt text](images3/image-50.png)
![alt text](images3/image-51.png)
Y finalmente se despliega con netlify deploy --prod. <br>
![alt text](images3/image-52.png)
Se comprueba el despliegue. <br>
![alt text](images3/image-71.png)

## Despliegue mediante conexión con Github
Lo primero es eliminar la página creada en netlify y el repositorio que se habia clonado. <br>
![alt text](images3/image-58.png)
![alt text](images3/image-53.png)
Se descarga las fuentes en formato .zip. <br>
![alt text](images3/image-54.png)
Se crea un nuevo repositorio. <br>
![alt text](images3/image-55.png)
Se añade el contenido de la carpeta al repositorio. <br>
![alt text](images3/image-57.png)
Ahora se procede a conectar el repositorio con NETLIFY, se autoriza todo y luego se selecciona el repositorio creado antes. <br>
![alt text](images3/image-59.png)
![alt text](images3/image-60.png)
![alt text](images3/image-61.png)
Se comprueba que el nombre está disponible. <br>
![alt text](images3/image-62.png)
Se introducen los siguientes comandos en los campos de datos y se le da a deploy. <br>
![alt text](images3/image-63.png) <br>
![alt text](images3/image-72.png)
Ahora se accede a la carpeta public y se modifica el archivo robot.txt, se pone el nombre en disallow, se sube al repositorio con un commit y ya estaría hecho. <br>
![alt text](images3/image-64.png)
![alt text](images3/image-65.png) 

## Despliegue en Vercel
En Vercel es muy similiar, lo primero es registrarse y autorizar a Github volviendo a seleccionar el repositorio deseado. <br>
![alt text](images3/image-66.png)
![alt text](images3/image-67.png)
![alt text](images3/image-68.png)
Se ponen los siguientes comandos y nombre y se le da a deploy. <br>
![alt text](images3/image-69.png)
![alt text](images3/image-73.png)
Por último se vuelve a modificar el robot.txt, se hace commit y ya estaría terminado
![alt text](images3/image-70.png)