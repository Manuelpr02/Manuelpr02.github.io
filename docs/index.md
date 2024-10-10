# Práctica 2.1 – Instalación y configuración de servidor web Nginx

Práctica realizada por Manuel Peñas Redondo 2º DAW - B

## Instalación servidor web Nginx
Lo primero es actualizar los repositorios. <br>

![alt text](image-2.png)

Se instala el paquete de nginx. <br>

![alt text](image-4.png)

Se comprueba que está bien instalado y se reinicia. <br>

![alt text](image-3.png)

## Creación de las carpeta del sitio web
Se crea la carpeta donde se almacenará el sitio web con el comando sudo mkdir -p /var/www/nombre_web/html
y se clona el repositorio. Si da fallo por el git es porque hay que instalar su paquete. <br>

![alt text](image.png)

Se le da la propiedad de la carpeta al usuario del servicio web y se le dan los permisos. <br>

![alt text](image-5.png)

Se busca la ip para comprobar el funcionamiento. <br>

![alt text](image-6.png)

Desde Windows en este caso se comprueba que el servidor funciona. <br>

![alt text](image-8.png)

## Configuración de servidor web NGINX
Para configurar el servidor se modifican primero los archivos de los hots virtuales añadiendo las siguientes líneas. <br>

![alt text](image-9.png)

Y se crea el archivo simbólico entre los sitios habilitados y dicho artículo modificado.
Por último se reinicia para que se aplique la modificación. <br>

![alt text](image-10.png)

## Comprobaciones
### Comprobación del correcto funcionamiento
Lo primero es modificar el archivo hosts de Windows añadiendo la IP de la máquina virtual. <br>

![alt text](image-13.png)

### Comprobar registros del servidor
Ahora se comprueban los archivos logs y sus rutas. Primero los de acceso: <br>

![alt text](image-11.png)

Y luego los de error: <br>

![alt text](image-12.png)

## FTP
### Configurar servidor SFTP en Debian
Primero se instala. <br>

![alt text](image-14.png)

Se crea la carpeta para almacenarlo y los certificados de seguridad. <br>

![alt text](image-15.png)

Se modifica el fichero de configuración y se añaden las siguientes líneas. <br>

![alt text](image-16.png)

Ahora para la comprobación se descarga Filezilla en Windows y se introducen los datos de la máquina virtual y el puerto 21 y se le da a conexión rápida. <br>

![alt text](image-17.png)

Si se conecta saldrá los directorios de la máquina virtual en la derecha. <br>

![alt text](image-18.png)

Se clica en la carpeta descargas y se ve la conexión donde se sube algún archivo. <br>

![alt text](image-19.png)

Se descarga el paquete para descomprimir ZIP si no se tiene. <br>

![alt text](image-20.png)

## HTTPS
Se genera el certificado SSL y la clave privada. <br>

![alt text](image-21.png)

Se crea el fichero Diffie-Hellman. <br>

![alt text](image-22.png)

Se modifica añadiendo las siguientes líneas. <br>

![alt text](image-23.png)

Se crea otro archivo para dar más seguridad con las siguientes líneas. <br>

![alt text](image-24.png)

Por último se modifica el nginx para HTTPS con las siguientes líneas. <br>

![alt text](image-25.png)

Se guarda el archivo y se reinicia. <br>

![alt text](image-26.png)

Se comprueban los ficheros de accesso y de error para visualizar la conexión. <br>

![alt text](image-27.png)

Por último se comprueba el funcionamiento desde Windows. Se pone HTTP:// y el dominio y se pulsa enter. <br>

![alt text](image-28.png)

Se comprueba que lo redirecciona a HTTPS y funciona. <br>

![alt text](image-29.png)

## Cuestiones finales

#### 1. ¿Qué pasa si no hago el link simbólico entre sites-available y sites-enabled de mi sitio web?

Si no haces el link simbólico, Nginx no sabrá que el sitio web está disponible para servir, y no se podrá acceder a él.

#### 2. ¿Qué pasa si no le doy los permisos adecuados a /var/www/nombre_web?

Sin los permisos adecuados, Nginx no podrá servir tu sitio web, y se expondrá a problemas de seguridad. 