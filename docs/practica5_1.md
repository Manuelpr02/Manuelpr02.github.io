# Enunciado ejercicios Git y GitHub I y II

## Repositorio DEAW
Lo primero es crear el repositorio público en Github con el nombre de DEAW. <br>
![alt text](images4/image.png) <br>
Se clona dentro de una carpeta. <br>
![alt text](images4/image-1.png) <br>
## README
Se crea un README.md con contenido. <br>
![alt text](images4/image-2.png)<br>
## Commit inicial
Se crea el commit para la subida. <br>
![alt text](images4/image-3.png)<br>
## Push inicial
Se sube al repositorio con git push y se comprueba como se ha subido. <br>
![alt text](images4/image-4.png) <br>
![alt text](images4/image-5.png) <br>
## Ignorar archivos
Se crea un fichero privado.txt y una carpeta llamada privada y se añade dentro del .gitignore para que lo ignore. <br>
![alt text](images4/image-6.png) <br>
Se sube y se comprueba que no se hayan subido el fichero y la carpeta. <br>
![alt text](images4/image-7.png) <br>
## Añadir fichero 1.txt
Se crea un fichero 1.txt y se añade con git add. <br>
![alt text](images4/image-8.png) <br>
## Crear el tag v0.1
Se crea un tag con git tag y se añade. <br>
![alt text](images4/image-9.png) <br>
## Subir el tag v0.1
Se sube con git push el tag. <br>
![alt text](images4/image-10.png) <br>
## Cuenta de GitHub
Se cambia la foto de perfil dentro del propio Github y se añade la doble autentificación. <br>
![alt text](images4/image-11.png) <br>
![alt text](images4/image-12.png) <br>
## Crear una tabla
Se modifica el Readme añadiendo nuevos usuarios y su correo y se sube. <br>
![alt text](images4/image-13.png) <br>
## Colaboradores 
Se invita como colaborador a un usuario dentro de Github. <br>
![alt text](images4/image-14.png) <br>
## Crear una rama v0.2
Se crea una rama con git branch. <br>
![alt text](images4/image-15.png) <br>
## Añadir fichero 2.txt
Se crea un fichero 2.txt y se sube al repositorio y se comprueba su subida. <br>
![alt text](images4/image-16.png) <br>
![alt text](images4/image-17.png) <br>
## Merge directo
Se cambia a la rama main y se hace un merge llamado v0.2 . <br>
![alt text](images4/image-18.png) <br>
## Merge con conflicto
Se modifica los ficheros creados antes poniendo hola y adiós y se suben y se fusionan las ramas. <br>
![alt text](images4/image-19.png) <br>
## Listado de ramas
Se muestra las ramas con git branch. <br>
![alt text](images4/image-20.png) <br>
## Arreglar conflicto
Se modifica el fichero y se añade solucionando el conflicto. <br> 
![alt text](images4/image-21.png) <br> 
![alt text](images4/image-22.png) <br> 
## Borrar rama
Ahora se crea el tag v0.2 y se sube. <br> 
![alt text](images4/image-23.png) <br> 
Y luego se elimina la rama v0.2. <br> 
![alt text](images4/image-24.png) <br> 
## Listado de cambios
Se muestran todos los cambios con git log --oneline --decorate -graph -all. <br> 
![alt text](images4/image-25.png) <br> 



## Ejercicios de creación y actualización de repositorios
#### Ejercicio 1
Se configura Git aladiendo usuario, el correo y activando el color de salida. <br> 
![alt text](images4/image-26.png) <br> 
#### Ejercicio 2
Se crea el repositorio libro y se muestra el contenido. <br> 
![alt text](images4/image-27.png) <br> 
#### Ejercicio 3
Se crea indice.txt con la información de la imagen y se sube a la zona de intercambio temporal. <br> 
![alt text](images4/image-28.png) <br> 
#### Ejercicio 4
Se realiza el commit de la imagen y se sube. <br> 
![alt text](images4/image-29.png) <br> 
#### Ejercicio 5
Se modifica el fichero de antes con la nueva información y se muestran las diferencias con la versión anterior. Luego se hace el commit. <br> 
![alt text](images4/image-30.png) <br> 
#### Ejercicio 6
Se muestra los cambios con la versión anterior, se modifica el mensaje del commit y se vuelven a mostrar los cambios. <br> 
![alt text](images4/image-31.png) <br> 
## Ejercicios de manejo del historial de cambios
#### Ejercicio 1
Se muestra el historial de cambios, se crea la carpeta capitulos y dentro el fichero capitulo1.txt con la información de la imagen de debajo. Finalmente se hace el commit y se muestra el historial. <br>
![alt text](images4/image-33.png) <br>
![alt text](images4/image-32.png) <br>
#### Ejercicio 2
Se crea el fichero capitulo2.txt con la información de debajo, se sube, se crea el commit y se muestra la diferencia entre esta versión y dos anteriores. <br>
![alt text](images4/image-34.png) <br>
![alt text](images4/image-35.png) <br>
#### Ejercicio 3
Se crea el fichero capitulo3.txt con la información de debajo se sube sube, se hace el commit y se muestra la diferencia entre la primera y última versión. <br>
![alt text](images4/image-36.png) <br>
![alt text](images4/image-37.png) <br>
#### Ejercicio 4
Se modifica indice.txt añadiendo la nueva línea, se crea el commit y se comprueba quien lo ha modificado con git blame. <br>
![alt text](images4/image-38.png) <br>
![alt text](images4/image-39.png) <br>
## Ejercicios de deshacer cambios
#### Ejercicio 1
Se elimina la última linea de indice.txt se comprueba el estado y se vuelve a la versión anterior con git restore. <br>
![alt text](images4/image-40.png) <br>
![alt text](images4/image-41.png) <br>
#### Ejercicio 2
Se elimina la última línea de indice.txt, se sube, se comprueba el estado del repositorio, se quitan los cambios de la zona de intercambio temporal, se comprueba el estado y se vuelve a la versión original. <br>
![alt text](images4/image-42.png) <br>
![alt text](images4/image-43.png) <br>
#### Ejercicio 3
Se elimina la última linea de indice.txt, se guarda, se elimina el fichero capitulo3.txt, se añade uno nuevo llamado capitulo4.txt y se sube, se comprueba estado y se vuelve a la versión original. <br>
![alt text](images4/image-44.png) <br>
![alt text](images4/image-45.png) <br>
#### Ejercicio 4
Se elimina la última línea de indice.txt, se elimina el fichero capitulo3.txt y se sube con el commit de la imagen, se comprueba el estado y se deshacen los cambios y se vuelve a hacer el mismo commit. Se vuelven a deshacer los cambios y se comprueba el historial y el estado. <br>
![alt text](images4/image-46.png) <br>
![alt text](images4/image-47.png) <br>
## Ejercicios de gestión de ramas
#### Ejercicio 1
Se crea la rama bibliografía y se muestran las ramas existentes. <br>
![alt text](images4/image-48.png) <br>
#### Ejercicio 2
Se crea el fichero capitulo4.txt con la información de debajo y se sube a la zona de intercambio temporal haciendo el commit y mostrando el historial. <br>
![alt text](images4/image-49.png) <br>
![alt text](images4/image-50.png) <br>
#### Ejercicio 3
Se cambia a la rama creada antes y se crea el fichero bibliografía.txt con la información de debajo y se sube haciendo el commit y mostrando el historial. <br>
![alt text](images4/image-51.png) <br>
![alt text](images4/image-52.png) <br>
#### Ejercicio 4
Se fusiona con la rama master, luego se muestra el historial, se elimina la rama bibliografía y se muestra el historial de nuevo. <br>
![alt text](images4/image-53.png) <br>
#### Ejercicio 5
Se crea la rama bibliografía y se cambia modificando el fichero como en la segunda imagen de debajo, se añaden los cambios con el commit y se cambia a la rama master donde se modifica el mismo fichero como en la tercera imagen. Por último se fusionan las ramas y se modifica el conflicto como en la cuarta imagen y se sube haciendo el commit y mostrando el historial por último. <br>
![alt text](images4/image-57.png) <br>
![alt text](images4/image-54.png) <br>
![alt text](images4/image-55.png) <br>
![alt text](images4/image-56.png) <br>
## Ejercicios de repositorios remotos
#### Ejercicio 1
Se crea el nuevo repositorio en GitHub. <br>
![alt text](images4/image-58.png) <br>
Se clona el repositorio en libro. <br>
![alt text](images4/image-59.png) <br>
#### Ejercicio 2
Se sube todo lo de libro haciendo el commit y se comprueba que está subido. <br>
![alt text](images4/image-60.png) <br>
![alt text](images4/image-61.png) <br>
#### Ejercicio 3
Se clona otro repositorio y se sube este fichero con el nombre y correo del autor. <br>
![alt text](images4/image-62.png) <br>
#### Ejercicio 4
Por último se hace una bifurcación en fork, se clona luego creando la rama auditoria y activandola y modificando el fichero de autores con el nombre para finalmente subirlo todo con el commit. <br>
![alt text](images4/image-63.png) <br>
![alt text](images4/image-64.png) <br>
![alt text](images4/image-65.png) <br>