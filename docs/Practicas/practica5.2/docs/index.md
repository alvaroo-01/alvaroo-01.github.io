# Practica 5.1
# Ejercicios Git y GitHub 2

## Ejercicios de creación y actualización de repositorios

### Ejercicio 1

Configurar Git definiendo el nombre del usuario, el correo electrónico y activar el coloreado de la salida.

Mostrar la configuración final.

![captura1](assets/images/1.PNG)

### Ejercicio 2

Crear un repositorio nuevo con el nombre libro y mostrar su contenido.

![captura2](assets/images/2.PNG)

### Ejercicio 3

Comprobar el estado del repositorio.

Crear un fichero indice.txt con el siguiente contenido:
>Capítulo 1: Introducción a Git
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Repositorios remotos

Comprobar de nuevo el estado del repositorio.
Añadir el fichero a la zona de intercambio temporal.

Volver a comprobar una vez más el estado del repositorio.

![captura3](assets/images/3.PNG)
![captura4](assets/images/4.PNG)
![captura5](assets/images/5.PNG)

### Ejercicio 4

Realizar un commit de los últimos cambios con el mensaje *“Añadido índice del libro.”* y ver el estado del repositorio.

![captura6](assets/images/6.PNG)

### Ejercicio 5

Cambiar el fichero indice.txt para que contenga lo siguiente:

>Capítulo 1: Introducción a Git
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos

Mostrar los cambios con respecto a la última versión guardada en el repositorio.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 3 sobre gestión de ramas”*.

![captura7](assets/images/7.PNG)
![captura8](assets/images/8.PNG)
![captura9](assets/images/9.PNG)

### Ejercicio 6

Mostrar los cambios de la última versión del repositorio con respecto a la anterior.

Cambiar el mensaje del último commit por *“Añadido capítulo 3 sobre gestión de ramas al índice.”*

Volver a mostrar los últimos cambios del repositorio.

![captura10](assets/images/10.PNG)


## Ejercicios de manejo del historial de cambios

### Ejercicio 1

Mostrar el historial de cambios del repositorio.

Crear la carpeta capitulos y crear dentro de ella el fichero capitulo1.txt con el siguiente texto.

>Git es un sistema de control de versiones ideado por Linus Torvalds.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 1.”* Volver a mostrar el historial de cambios del repositorio.

![captura11](assets/images/11.PNG)
![captura12](assets/images/12.PNG)
![captura13](assets/images/13.PNG)


### Ejercicio 2

Crear el fichero capitulo2.txt en la carpeta capitulos con el siguiente texto.

>El flujo de trabajo básico con Git consiste en: 1- Hacer cambios en el repositorio. 2- Añadir los cambios a la zona de intercambio temporal. 3- Hacer un commit de los cambios.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 2.”*

Mostrar las diferencias entre la última versión y dos versiones anteriores.

![captura14](assets/images/14.PNG)
![captura15](assets/images/15.PNG)
![captura16](assets/images/16.PNG)


### Ejercicio 3

Crear el fichero capitulo3.txt en la carpeta capitulos con el siguiente texto.

>Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 3.”*

Mostrar las diferencias entre la primera y la última versión del repositorio.

![captura17](assets/images/17.PNG)
![captura18](assets/images/18.PNG)
![captura19](assets/images/19.PNG)


### Ejercicio 4

Añadir al final del fichero indice.txt la siguiente línea:

>Capítulo 5: Conceptos avanzados

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 5 al índice.”*.

Mostrar quién ha hecho cambios sobre el fichero indice.txt.

![captura20](assets/images/20.PNG)
![captura21](assets/images/21.PNG)
![captura22](assets/images/22.PNG)


## Ejercicios de deshacer cambios

### Ejercicio 1

Eliminar la última línea del fichero indice.txt y guardarlo.

Comprobar el estado del repositorio.

Deshacer los cambios realizados en el fichero indice.txt para volver a la versión anterior del fichero.

Volver a comprobar el estado del repositorio.

![captura23](assets/images/23.PNG)

### Ejercicio 2

Eliminar la última línea del fichero indice.txt y guardarlo.

Añadir los cambios a la zona de intercambio temporal.

Comprobar de nuevo el estado del repositorio.

Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

Comprobar de nuevo el estado del repositorio.

Deshacer los cambios realizados en el fichero indice.txt para volver a la versión anterior del fichero.

Volver a comprobar el estado del repositorio.

![captura24](assets/images/24.PNG)

### Ejercicio 3

Eliminar la última línea del fichero indice.txt y guardarlo.

Eliminar el fichero capitulos/capitulo3.txt.

Añadir un fichero nuevo capitulos/capitulo4.txt vacío.

Añadir los cambios a la zona de intercambio temporal.

Comprobar de nuevo el estado del repositorio.

Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

Comprobar de nuevo el estado del repositorio.

Deshacer los cambios realizados para volver a la versión del repositorio.

Volver a comprobar el estado del repositorio.

![captura25](assets/images/25.PNG)

### Ejercicio 4

Eliminar la última línea del fichero indice.txt y guardarlo.

Eliminar el fichero capitulos/capitulo3.txt.

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Borrado accidental.”

Comprobar el historial del repositorio.

Deshacer el último commit pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal.

Comprobar el historial y el estado del repositorio.

Volver a hacer el commit con el mismo mensaje de antes.

Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.

Comprobar de nuevo el historial y el estado del repositorio.

![captura26](assets/images/26.PNG)

## Ejercicios de gestión de ramas

### Ejercicio 1

![captura27](assets/images/27.PNG)

### Ejercicio 2

Crear el fichero capitulos/capitulo4.txt y añadir el texto siguiente

>En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje *“Añadido capítulo 4.”*

Mostrar la historia del repositorio incluyendo todas las ramas.

![captura28](assets/images/28.PNG)
![captura29](assets/images/29.PNG)
![captura30](assets/images/30.PNG)

### Ejercicio 3

Cambiar a la rama bibliografia.

Crear el fichero bibliografia.txt y añadir la siguiente referencia

>Chacon, S. and Straub, B. Pro Git. Apress.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje *“Añadida primera referencia bibliográfica.”*

Mostrar la historia del repositorio incluyendo todas las ramas.

![captura31](assets/images/31.PNG)
![captura32](assets/images/32.PNG)
![captura33](assets/images/33.PNG)

### Ejercicio 4

Fusionar la rama bibliografia con la rama master.

Mostrar la historia del repositorio incluyendo todas las ramas.

Eliminar la rama bibliografia.

Mostrar de nuevo la historia del repositorio incluyendo todas las ramas.

![captura34](assets/images/34.PNG)

### Ejercicio 5

Crear la rama bibliografia.

Cambiar a la rama bibliografia.

Cambiar el fichero bibliografia.txt para que contenga las siguientes referencias:


>Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”

Cambiar a la rama master.

Cambiar el fichero bibliografia.txt para que contenga las siguientes referencias:


>Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje *“Añadida nueva referencia bibliográfica.”*

Fusionar la rama bibliografia con la rama master.

Resolver el conflicto dejando el fichero bibliografia.txt con las referencias:


>Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
Hodson, R. Ry’s Git Tutorial. Smashwords (2014)

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje *“Resuelto conflicto de bibliografía.”*

Mostrar la historia del repositorio incluyendo todas las ramas.

![captura35](assets/images/35.PNG)
![captura36](assets/images/36.PNG)
![captura37](assets/images/37.PNG)
![captura38](assets/images/38.PNG)
![captura39](assets/images/39.PNG)
![captura40](assets/images/40.PNG)
![captura41](assets/images/41.PNG)

## Ejercicios de repositorios remotos

### Ejercicio 1

Crear un nuevo repositorio público en GitHub con el nombre libro-git.

Añadirlo al repositorio local del libro.

Mostrar todos los repositorios remotos configurados.

![captura42](assets/images/42.PNG)
![captura43](assets/images/43.PNG)


### Ejercicio 2

Añadir los cambios del repositorio local al repositorio remoto de GitHub.

Acceder a GitHub y comprobar que se han subido los cambios mostrando el historial de versiones.

![captura44](assets/images/44.PNG)
![captura45](assets/images/45.PNG)

### Ejercicio 3

Colaborar en el repositorio remoto libro-git de otro usuario.

Clonar su repositorio libro-git.

Añadir el fichero autores.txt que contenga el nombre del usuario y su correo electrónico.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje *“Añadido autor.”*

Subir los cambios al repositorio remoto.

![captura46](assets/images/46.PNG)
![captura47](assets/images/47.PNG)
![captura48](assets/images/48.PNG)
![captura49](assets/images/49.PNG)
![captura50](assets/images/50.PNG)


### Ejercicio 4

Hacer una bifurcación del repositorio remoto asalber/libro-git en GitHub.

Clonar el repositorio creado en la cuenta de GitHub del usuario.

Crear una nueva rama autoria y activarla.

Añadir el nombre del usuario y su correo al fichero autores.txt.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “Añadido nuevo autor.”

Subir los cambios de la rama autoria al repositorio remoto en GitHub.

Hacer un Pull Request de los cambios en la rama autoria.

![captura51](assets/images/51.PNG)
![captura52](assets/images/52.PNG)
![captura53](assets/images/53.PNG)
![captura54](assets/images/54.PNG)
![captura55](assets/images/55.PNG)
