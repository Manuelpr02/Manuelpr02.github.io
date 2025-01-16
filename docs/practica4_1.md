# Práctica 4.1 - Configuración de un servidor DNS

## Instalación de servidor DNS
Lo primero es conectarse por SSH a la máquina física como se muestra en la foto. <br>
![alt text](/images3/image-74.png)
Una vez conectado, se instala el servidor DNS con el siguiente comando. <br>
![alt text](/images3/image-75.png)

## Configuración del servidor
Lo primero para configurarlo es modificar el archivo named como se muestra en la imagen para indicar que solo se puede utilizar IPv4. <br>
![alt text](/images3/image-76.png)
Para comprobar que la configuración es correcta se mira que el siguiente archivo tenga las mismas líneas que la imagen. <br>
![alt text](/images3/image-77.png)

### Configuración named.conf.options
Para configurar el archivo named.conf.options se hace una copia de seguridad de emergencia lo primero. <br>
![alt text](/images3/image-78.png)
Ahora se añade las primeras líneas para indicar que solo la ip que se usa sea aceptada. Lo único que se modifica es el tercer dígito que se pone el de la propia red y luego el resto de líneas tienen que quedar como en la imagen para dar permisos o no a los clientes y para habilitar el DNSSEC.<br>
![alt text](/images3/image-79.png)
Una vez modificado se comprueba que funciona y se reinicia para guardar las modificaciones. <br>
![alt text](/images3/image-80.png)

### Configuración named.conf.local
Se habilita la zona deaw.es  y se indica que el servidor es maestro para la zona, indicando la ruta donde se encuentra el archivo. <br>
![alt text](/images3/image-81.png)   

### Creación del archivo de zona
Se crea el archivo en la ruta indicada antes con las siguientes características manteniendo la forma del texto. <br>
![alt text](/images3/image-82.png)

### Creación del archivo de zona para la resolución inversa
Se añade ahora la zona nueva con la IP de la red y se indica la ruta del archivo. <br>
![alt text](/images3/image-83.png)
Nuevamente se crea el archivo con los siguientes datos manteniendo la estructura del texto. <br>
![alt text](/images3/image-84.png)

### Comprobación de las configuraciones
Para comprobar la configuración se ejecutan los siguientes comandos. Primero se comprueba cada zona de forma individual y luego relacionándolas. Si devuelve OK estará correcto. <br>
![alt text](/images3/image-85.png)
![alt text](/images3/image-86.png)
Una vez comprobado se reinicia el servidor para guardar los cambios. <br>
![alt text](/images3/image-87.png)

### Comprobación de las resoluciones y de las consultas
Para finalizar las comprobaciones se modifica el siguiente archivo añadiendo la IP de casa para establecer el cliente. <br>
![alt text](/images3/image-88.png)
Por último se hace la comprobación primero con dig, se hace con deaw.es y sale como en la imagen donde indica que se ha producido una respuesta y luego con la IP saldría igual. <br>
![alt text](/images3/image-89.png)
Y con nslookup se hace como en la imagen con deaw.es y con la IP se haría igual. <br>
![alt text](/images3/image-90.png)

## Cuestiones
#### Cuestión 1. ¿Qué pasará si un cliente de una red diferente a la tuya intenta hacer uso de tu DNS de alguna manera, le funcionará?¿Por qué, en qué parte de la configuración puede verse?
No porque se restringe a clientes confiables con la directiva allow-recursion {confiables;}; y solo mi IP está registrada.

#### Cuestión 2. ¿Por qué tenemos que permitir las consultas recursivas en la configuración?
Para que el servidor pueda resolver los nombres de dominios que no están en su zona autoritaria.

#### Cuestión 3. El servidor DNS que acabáis de montar, ¿es autoritativo?¿Por qué?
Sí porque se indica type master en la zona específica.

#### Cuestión 4. ¿Dónde podemos encontrar la directiva $ORIGIN y para qué sirve?
Se encuentra en los archivos de zona DNS y se encarga de definir el dominio raíz de los registros del archivo. 

#### Cuestión 5. ¿Una zona es idéntico a un dominio?
No, un dominio puede dividirse en múltiple zonas porque el dominio es el conjunto de nombre y subdominios bajo un TLD

#### Cuestión 6. ¿Pueden editarse los archivos de zona de un servidor esclavo/secundario?
Directamente no, se debe hacer desde el servidor maestro.

#### Cuestión 7. ¿Por qué podría querer tener más de un servidor esclavo para una misma zona?
Por si falla uno tener otro disponible, para tener un balanceo de carga y para evitar la redundancia de datos. 

#### Cuestión 8. ¿Cuántos servidores raíz existen?
Existen 13 servidores raíz.

#### Cuestión 9. ¿Qué es una consulta iterativa de referencia?
Una consulta iterativa de referencia es cuando un servidor DNS no realiza una búsqueda completa por sí mismo y responde con la dirección de otro servidor DNS más específico. 

#### Cuestión 10. En una resolución inversa, ¿a qué nombre se mapearía la dirección IP 172.16.34.56?
Se mapearía como 56.34.16.172.in-addr.arpa.