# Práctica Ampliada

## Instalación de Nginx y preparación.
Lo primero se conecta por ssh a la máquina desde Windows. <br>
![alt text](images2/image-39.png)
Como ya estaba nginx instalado de prácticas anteriores se comprueba la versión. <br>
![alt text](images2/image-40.png)

## Creación de usuarios del sistema.
Se procede ahora a la creación de los usuarios con sus contraseñas usando el comando useradd. En este caso los usuarios se llamarán Usuario1 y Usuario2. <br>
![alt text](images2/image-41.png)

## Estructura de carpetas y archivos.
Dentro de cada usuario se crea una carpeta en home llamada public_html con el comando mkdir. <br>
![alt text](images2/image-42.png)
Se le asignan los permisos para que Nginx pueda acceder a ellas con el comando setfacl -d -R -m u:www-data:rw public_html. Se hace en ambas carpetas y se muestra que se ha asignado correctamente con el comando getfacl public_html.<br>
![alt text](images2/image-43.png)
![alt text](images2/image-44.png)
Ahora se crean dos html sencillos en cada carpeta y que sean diferentes. Esto se hace para poder comprobar luego que las páginas web de cada usuario se pueden desplegar. <br>
![alt text](images2/image-46.png)
![alt text](images2/image-45.png)

## Creación y configuración de los hosts.
Se crean los certificados a cada usuario mediante el comando openssl req -x509 -newkey rsa:4096 -keyout /etc/ssl/private/usuario.pem -out /etc/ssl/certs/usuario.pem -sha256 -days 365 --nodes, con el nombre de cada usuario.pem. <br>
![alt text](images2/image-48.png)
![alt text](images2/image-49.png)

Ahora se crean los archivos de configuración para cada usuario en la carpeta /etc/nginx/sites-available, implementando la conexión segura por HTTPS e indicando el nombre de la página web que habra que buscar. <br>
![alt text](images2/image-50.png)
![alt text](images2/image-51.png)

Ahora se crea el enlace simbólico de ambos con la carpeta enabled mediante el comando ln -s /etc/nginx/sites-available/nombreweb /etc/nginx/sites-enabled/nombreweb. <br>
![alt text](images2/image-52.png)
![alt text](images2/image-53.png)

Por último se añade la ip y el nombre de las páginas al archivo host de windows para que puedan buscarse dichas páginas. <br>
![alt text](images2/image-54.png)

## Comprobación.
Para finalizar la práctica busca ambas páginas web en windows mediante el nombre asignado en el archivo de configuración y se verifica que todo está correcto y funciona. <br>
![alt text](images2/image-55.png)
![alt text](images2/image-56.png)