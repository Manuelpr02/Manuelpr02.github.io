# Práctica 2.3 – Proxy inverso con Nginx

Primero se clona la máquina generando nuevas direcciones MAC. <br>
![alt text](images/image-55.png)
![alt text](images/image-56.png)
<br>
En la máquina donde estaba el servidor se le cambia el nombre a webserver al archivo de configuración, se le cambia el puerto por el 8080 y se le añade un header para la futura comprobación. <br>
![alt text](images/image-61.png)

![alt text](images/image-86.png)
Finalmente se elimina el enlace simbólico que había y se crea uno nuevo, luego se reinicia nginx.
<br>
![alt text](images/image-63.png)
![alt text](images/image-65.png)
En el hosts de Windows se cambia la IP por la nueva máquina que va a hacer de proxy y se cambia el nombre.
<br>
![alt text](images/image-87.png)
Se crea un fichero de archivo nuevo donde se mantiene el puerto 80, el nombre se le asigna el del hosts y en location se le añade un header y la dirección donde se redirige.
<br>
![alt text](images/image-88.png)
También se le añade al hosts de la máquina con la ip del servidor.
<br>
![alt text](images/image-89.png) 
<br>
Por último se comprueba buscando en Firefox, pulsando F12, en red desactivando la caché y pulsando en el primero. Y en las cabeceras se ve ambos header antes añadidos. También se comprueba el access.log para verificar que se han conectado.
<br>
![alt text](images/image-90.png)
![alt text](images/image-91.png)