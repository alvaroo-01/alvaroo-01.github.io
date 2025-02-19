# Practica 6.2
# Despliegue de una aplicación PHP con Nginx y MySQL usando Docker y docker-compose

## Estructura de directorios

Según el guión de la práctica necesitamos tener la siguiente estructura de archivos:

![captura1](assets/images/2.PNG)

Así pues, la creamos:

![captura2](assets/images/1.PNG)

## Creación de un contenedor Nginx

En el archivo `docker-compose.yml` escribimos lo que se nos indica en el guión:

![captura3](assets/images/3.PNG)
*Nota: he escogido ese puerto porque ya hay un servicio en activo en el puerto 80:80*

Y levantamos el contenedor:

![captura4](assets/images/4.PNG)

*Comprobación: `http://localhost:8081`*

![captura5](assets/images/5.PNG)

## Creación de un Contenedor PHP

Ahora tenemos que modificar los siguientes archivos:

1. `www/html/index.php`
2. `nginx/default.conf`
3. `nginx/Dockerfile`

En `www/html/index.php`, escribimos lo siguiente:

![captura6](assets/images/6.PNG)

En `nginx/default.conf`:

![captura7](assets/images/7.PNG)

En `nginx/Dockerfile`:

![captura8](assets/images/8.PNG)

Tras esto modificamos el `docker-compose.yml`:

![captura9](assets/images/9.PNG)

Y, de nuevo, levantamos el contenedor:

![captura10](assets/images/10.PNG)
*Nota: El error que sale a mitad se debe a que tuve que cambiar de nuevo el puerto.*
![captura11](assets/images/11.PNG)

*Comprobación: `http://localhost:8081`*
![captura12](assets/images/12.PNG)

## Creación de un Contenedor para Datos

Modificamos de nuevo el `docker-compose.yml` y comprobamos que funciona al levantarlos:

![captura13](assets/images/13.PNG)

![captura14](assets/images/15.PNG)

## Creación de un Contenedor MySQL

Escribimos en `php/Dockerfile` según el guión:

![captura16](assets/images/16.PNG)

Y volvemos a editar el `docker-compose.yml`:

![captura17](assets/images/17.PNG)

Y esta vez, escribimos en `www/html/index.php` lo siguiente:

![captura18](assets/images/18.PNG)

Otra vez, levantamos el contenedor:

![captura19](assets/images/19.PNG)
![captura20](assets/images/20.PNG)
![captura21](assets/images/21.PNG)

## Verificación de Conexión a la Base de Datos

*Comprobación: `http://localhost:8081`*
![captura22](assets/images/22.PNG)

Para acceder a las tablas de la base de datos tenemos que poner en `www/html/index.php`:

```
$user = 'root';
$password = 'secret';
```

![captura23](assets/images/23.PNG)

*Comprobación: `http://localhost:8081`*
![captura24](assets/images/24.PNG)