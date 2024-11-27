# Práctica 3.5: Despliegue de una aplicación Flask (Python)

## Instalaciones
Primero se actualiza los paquetes y se instala el gestor de paquetes de Python. <br>
![alt text](/images2/image-1.png)
Luego se instala el paquete pipenv para entornos virtuales. <br>
![alt text](/images2/image-2.png) <br>
Se crea el directorio para el proyecto, se le da los permisos para que el propio usuario sea el dueño y pertenezca al grupo www-data. Luego se le dan permisos y se crea un archivo oculto. <br>
![alt text](/images2/image-4.png)

## Despliegue con Flask inicial
Se edita con las siguientes variables. <br>
![alt text](/images2/image-5.png)
![alt text](/images2/image-6.png)
Se inicia el entorno virtual que carga las variables del fichero .env y se instalan las dependecias necesarias. <br>
![alt text](/images2/image-7.png)<br>
Se crea una aplicación sencilla que tendrá los siguientes archivos. <br>
![alt text](/images2/image-8.png) <br>
Se editan los archivos para que queden así: <br>
![alt text](/images2/image-9.png)
![alt text](/images2/image-10.png) <br>
Se ejecuta la aplicación. <br>
![alt text](/images2/image-11.png)
Se comprueba en la máquina anfitrión con la ip de la virtual y el puerto 5000. <br>
![alt text](/images2/image-12.png)
Ahora se comprueba que gunicorn funciona con el comando: gunicorn --workers 4 --bind 0.0.0.0:5000 wsgi:app. Después se obtiene la ruta para configurar más adelante. Por último se para el entorno virtual. <br>
![alt text](/images2/image-13.png)

## Despliegue con Nginx inicial
Suponiendo que está instalado Nginx de prácticas anteriores se inicia y se comprueba que está activo. <br>
![alt text](/images2/image-14.png)
Se crea un fichero en systemd y se rellena así pero usando los datos de cada uno como la ruta de antes. <br>
![alt text](/images2/image-15.png)
Ahora se habilita y se inicia el servicio. <br>
![alt text](/images2/image-17.png)
Ahora como en prácticas anteriores se crea un archivo de configuración con los siguientes datos pero adaptados a cada usuario. <br>
![alt text](/images2/image-18.png)
Y se crea el enlace simbólico comprobando su creación. <br>
![alt text](/images2/image-19.png)
Se reinicia nginx y se añade la ip y el server_name al fichero host de la maquina anfitriona. <br>
![alt text](/images2/image-20.png) <br>
Se comprueba que se ha desplegado. <br>
![alt text](/images2/image-21.png)

## Despliegue con Flask repositorio
Primero se clona el repositorio y se repite el proceso dándole los permisos oportunos. <br>
![alt text](/images2/image-22.png)
Luego se accede a la carpeta de la práctica, se crea el fichero .env y se modifica de nuevo. <br>
![alt text](/images2/image-23.png)
Se inicia el entorno virtual. <br>
![alt text](/images2/image-24.png)
Se instalan las dependecias. <br>
![alt text](/images2/image-25.png) <br>
![alt text](/images2/image-26.png)
Se modifican los ficheros y se inicia el entorno virtual. <br>
![alt text](/images2/image-28.png) <br>
Se comprueba que se ha desplegado bien. <br>
![alt text](/images2/image-29.png) <br>
Ahora se comprueba que gunicorn funciona con el comando: gunicorn --workers 4 --bind 0.0.0.0:5000 wsgi:app. Después se obtiene la ruta para configurar más adelante con which unicorn y por último se para el entorno virtual. <br>
![alt text](/images2/image-30.png)

## Despliegue con Nginx repositorio
Se crea el archivo en systemd con los nuevos datos. <br>
![alt text](/images2/image-32.png)
Se habilita y se inicia el servicio. <br>
![alt text](/images2/image-33.png)
Se crea el archivo de configuración con los siguientes datos. <br>
![alt text](/images2/image-34.png)
Se cra el archivo simbólico y se comprueba su existencia. <br>
![alt text](/images2/image-35.png)
Se actualiza el nginx. <br>
![alt text](/images2/image-36.png)
Se añade la ip de la máquina virtual y el server_name al archivo host de la máquina anfitriona. <br>
![alt text](/images2/image-37.png)<br>
Se comprueba que es correcto el despliegue. <br>
![alt text](/images2/image-38.png)
## Cuestiones 
#### Cuestion 1. Busca, lee, entiende y explica qué es y para que sirve un servidor WSGI
WSGI (Web Server Gateway Interface) es un estándar de interfaz entre servidores web y aplicaciones web o frameworks desarrollados en Python, diseñado para mejorar la interoperabilidad y la eficiencia de las aplicaciones web.
Sirve para que las aplicaciones web escritas en Python se comuniquen con servidores web como Nginx o Apache, actúa como un intermediario que traduce las solicitudes del servidor en un formato que la aplicación puede entender y luego devuelve la respuesta al cliente y es esencial para ejecutar aplicaciones web Python en producción, asegurando compatibilidad y buen rendimiento.