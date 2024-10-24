# Práctica 2.1 – Instalación y configuración de servidor web Nginx

Práctica realizada por Manuel Peñas Redondo 2º DAW - B

## Instalación servidor web Nginx
Lo primero es actualizar los repositorios. <br>

![alt text](images/image-2.png)

Se instala el paquete de nginx. <br>

![alt text](images/image-4.png)

Se comprueba que está bien instalado y se reinicia. <br>

![alt text](images/image-3.png)

## Creación de las carpeta del sitio web
Se crea la carpeta donde se almacenará el sitio web con el comando sudo mkdir -p /var/www/nombre_web/html
y se clona el repositorio. Si da fallo por el git es porque hay que instalar su paquete. <br>

![alt text](images/image-31.png)

Se le da la propiedad de la carpeta al usuario del servicio web y se le dan los permisos. <br>

![alt text](images/image-32.png)

Se busca la ip para comprobar el funcionamiento. <br>

![alt text](images/image-6.png)

Desde Windows en este caso se comprueba que el servidor funciona. <br>

![alt text](images/image-8.png)

## Configuración de servidor web NGINX
Para configurar el servidor se modifican primero los archivos de los hots virtuales añadiendo las siguientes líneas. <br>

![alt text](images/image-33.png)

Y se crea el archivo simbólico entre los sitios habilitados y dicho artículo modificado. <br>

Por último se reinicia para que se aplique la modificación.
![alt text](images/image-34.png)

## Comprobaciones
### Comprobación del correcto funcionamiento
Lo primero es modificar el archivo hosts de Windows añadiendo la IP de la máquina virtual. <br>

![alt text](images/image-30.png)

### Comprobar registros del servidor
Ahora se comprueban los archivos logs y sus rutas. Primero los de acceso: <br>

![alt text](images/image-11.png)

Y luego los de error: <br>

![alt text](images/image-12.png)

## FTP
### Configurar servidor SFTP en Debian
Primero se instala. <br>

![alt text](images/image-14.png)

Se crea la carpeta para almacenarlo y los certificados de seguridad. <br>

![alt text](images/image-15.png)

Se modifica el fichero de configuración y se añaden las siguientes líneas. <br>

![alt text](images/image-16.png)

Ahora para la comprobación se descarga Filezilla en Windows y se introducen los datos de la máquina virtual y el puerto 21 y se le da a conexión rápida. <br>

![alt text](images/image-17.png)

Si se conecta saldrá los directorios de la máquina virtual en la derecha. <br>

![alt text](images/image-18.png)

Se clica en la carpeta descargas y se ve la conexión donde se sube algún archivo. <br>

![alt text](images/image-19.png)

Se descarga el paquete para descomprimir ZIP si no se tiene. <br>

![alt text](images/image-20.png)

## HTTPS
Se genera el certificado SSL y la clave privada. <br>

![alt text](images/image-21.png)

Se crea el fichero Diffie-Hellman. <br>

![alt text](images/image-22.png)

Se modifica añadiendo las siguientes líneas. <br>

![alt text](images/image-23.png)

Se crea otro archivo para dar más seguridad con las siguientes líneas. <br>

![alt text](images/image-24.png)

Por último se modifica el nginx para HTTPS con las siguientes líneas. <br>

![alt text](images/image.png)

Se guarda el archivo y se reinicia. <br>

![alt text](images/image-26.png)

Se comprueban los ficheros de accesso y de error para visualizar la conexión. <br>

![alt text](images/image-27.png)



## Cuestiones finales

#### 1. ¿Qué pasa si no hago el link simbólico entre sites-available y sites-enabled de mi sitio web? <br>


Si no haces el link simbólico, Nginx no sabrá que el sitio web está disponible para servir, y no se podrá acceder a él.

#### 2. ¿Qué pasa si no le doy los permisos adecuados a /var/www/nombre_web? <br>


Sin los permisos adecuados, Nginx no podrá servir tu sitio web, y se expondrá a problemas de seguridad. 

# Práctica 2.2 - Autenticación en un servidor web Nginx

## Paquetes necesarios

Primero se comprueba que esté el paquete openssl instalado. <br>
![alt text](images/image-39.png)

## Creación de usuarios y contraseñas
Se crea los dos usuarios, aunque mi apellido es Peñas lo he puesto sin ñ para evitar errores y se crea una contraseña cifrada. <br>
![alt text](images/image-40.png)

Se comprueba que esté correctamente cifrado. <br>
![alt text](images/image-41.png)

## Autentificación básica

Se modifica el fichero de configuración para que pida autentificación al acceder. <br>
![alt text](images/image-42.png)

## Comprobación

Como se puede comprobar pide usuario y contraseña al acceder.<br>
![alt text](images/image-43.png)

Este es el mensaje que se muestra si no introduces algún dato correcto. <br>
![alt text](images/image-44.png)

Aquí se pueden comprobar los accesos correctos y erróneos de antes. <br>
![alt text](images/image-45.png)
![alt text](images/image-46.png)

## Tareas
Ahora para pedir autentificación de una parte de la página lo hacemos con la parte contactos, modificamos el archivo de configuración para que la pida ahí. <br>
![alt text](images/image-48.png)

Como se puede observar te pide autentificación y al acceder muestra la página de contactos. <br>
![alt text](images/image-49.png)
![alt text](images/image-47.png)

## Tareas combinación autentificación y restricción por IP
Primero se busca la ip de Windows y luego en el archivo de antes se le deniega el acceso. <br>
![alt text](images/image-50.png)

Y esto es lo que sale al intentar acceder y en el fichero de error de acceso. <br>
![alt text](images/image-51.png)
![alt text](images/image-52.png)

Por último se permite el acceso a una ip y se bloquea a las demás y se verifica que se puede acceder. <br>
![alt text](images/image-53.png)
![alt text](images/image-54.png)

## Cuestiones finales
#### Supongamos que yo soy el cliente con la IP 172.1.10.15 e intento acceder al directorio web_muy_guay de mi sitio web, equivocándome al poner el usuario y contraseña. ¿Podré acceder?¿Por qué? <br>

No podrás acceder porque la directiva satisfy all, obliga a que tanto la autentificación como la IP deben ser correctas. Y en este caso aunque esa IP sí este permitida el usuario sería erróneo <br>

#### ask "Cuestión 1" Supongamos que yo soy el cliente con la IP 172.1.10.15 e intento acceder al directorio web_muy_guay de mi sitio web, introduciendo correctamente usuari y contraseña. ¿Podré acceder?¿Por qué? <br>

En este caso sí podrás acceder porque se cumple que tanto la IP como la autentificación son correctos. <br>
#### Supongamos que yo soy el cliente con la IP 172.1.10.15 e intento acceder al directorio web_muy_guay de mi sitio web, introduciendo correctamente usuario y contraseña. ¿Podré acceder?¿Por qué? <br>

En este caso no podrás acceder porque la directiva any sólo permite que se cumpla una de las dos condiciones y en este caso tanto la IP como la autentificación son correctos. <br>

#### A lo mejor no sabéis que tengo una web para documentar todas mis excursiones espaciales con Jeff, es esta: Jeff Bezos y yo.  Supongamos que quiero restringir el acceso al directorio de proyectos porque es muy secreto, eso quiere decir añadir autenticación básica a la URL:Proyecto. Completa la configuración para conseguirlo: <br>

server {
    listen 80;
    listen [::]:80;
    root /var/www/freewebsitetemplates.com/preview/space-science;
    index index.html index.htm index.nginx-debian.html;
    server_name freewebsitetemplates.com www.freewebsitetemplates.com;

    location /Projects {
        auth_basic "Acceso restringido";
        auth_basic_user_file /etc/nginx/.htpasswd; 
        
        try_files $uri $uri/ =404;
    }
}

Se le añade la localización de los proyectos y se indica la autentificación <br>
