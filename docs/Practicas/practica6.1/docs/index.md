# Practica 6.1
# Dockerización del Despliegue de una Aplicación con Node.js

## Despliegue con Docker

Para esta práctica tendremos que instalar Docker, pero antes clonaremos el repositorio de Github del autor de los apuntes.

![captura1](assets/images/1.PNG)

Actualizamos e instalamos:

![captura2](assets/images/3.PNG)

![captura3](assets/images/2.PNG)

Ahora sí, podemos modificar el archivo `Dockerfile`. En un inicio, se ve tal que así:

![captura4](assets/images/4.PNG)

Tendremos que rellenar los espacios con las siguientes opciones:

![captura5](assets/images/5.PNG)

- RUN crea el directorio en el contenedor
- WORKDIR establece el directorio como directorio de trabajo
- COPY copia los ficheros `package.json` y `packa-lock.json` desde `src` al directorio de trabajo definido en WORKDIR
- Tras esto, se instalan las dependencias
- Se copia el resto de `src` al contenedor
- EXPOSE expone el puerto 3000 para acceder desde fuera del contenedor
- CMD indica el comando que se ejecutará al iniciar el contenedor.

Ejecutamos el comando siguiente para construir la imagen

![captura6](assets/images/6.PNG)

![captura7](assets/images/7.PNG)

Indicamos que escuche las peticiones en el puerto 3000:

![captura8](assets/images/8.PNG)

Y en caso de probar, la aplicación intentará conectarse a la base de datos que todavía no está configurada en el debido contenedor.

## Docker Compose

Instalamos Docker Compose.

![captura9](assets/images/9.PNG)

![captura10](assets/images/10.PNG)
*Nota: versión actual indicada*

Y verificamos que el archivo `docker-compose.yml` existe y tiene el contenido correcto:

![captura11](assets/images/11.PNG)
![captura12](assets/images/12.PNG)

Debemos crear la estructura de la base de datos (tablas, etc.):

![captura13](assets/images/13.PNG)

![captura14](assets/images/14.PNG)

Y levantar los contenedores:

![captura15](assets/images/15.PNG)

Introducimos el siguiente comando para testear:

![captura16](assets/images/16.PNG)
![captura17](assets/images/17.PNG)

## Tarea

*Probad que la aplicación junto con la BBDD funciona correctamente. El funcionamiento de la API es:*
*GET /persons/all muestra todas las personas en el libro de direcciones*
*GET /persons/1 muestra la persona con el id 1*
*PUT /persons/ añade una persona al libro de direcciones*
*DELETE /persons/1 elimina a la persona con el id 1*

*Ejemplos:*

 *curl -X PUT http://IP_APLICACION:3000/persons -H 'Content-Type: application/json' -d '{"id": 1, "firstName": "Raúl", "lastName": "Profesor"}'*

 *curl -X GET http://localhost:3000/persons -H 'Content-Type: application/json'*


![captura20](assets/images/20.PNG)