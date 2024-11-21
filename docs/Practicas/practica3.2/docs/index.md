# Practica 3.2
# Despliegue de aplicaciones con Node Express y en Netlify

## Node Express

Lo primero que tendremos que hacer será actualizar el sistema operativo:

![captura1](assets/images/nodejs/1.PNG)

También necesitaremos el paquete curl

![captura2](assets/images/nodejs/2.PNG)

![captura3](assets/images/nodejs/3.PNG)

![captura4](assets/images/nodejs/4.PNG)

Una vez hecho esto, podemos instalar nodejs:

![captura5](assets/images/nodejs/5.PNG)

![captura6](assets/images/nodejs/6.PNG)

*versiones de node y npm*

Ahora instalamos Express.js:

![captura7](assets/images/nodejs/7.PNG)

Nos creamos un directorio sobre el que clonar el repositorio indicado en la guía.

![captura8](assets/images/nodejs/8.PNG)

Y ejecutamos `npm install` para instalar las librerías y `npm run start` para iniciar la aplicación:

![captura9](assets/images/nodejs/9.PNG)

Tal y como indica la guía, nos encontramos con el error `sh: 1: nodemon: not found`.

![captura10](assets/images/nodejs/10.PNG)

El error es simple, no tenemos nodemon instalado (como se puede ver en la lista), por lo que tenemos que instalarlo:


![captura11](assets/images/nodejs/11.PNG)

*instalación global*

Al haberlo instalado globalmente tengo que comprobar en la variable `PATH` está incluido algo así como: `/usr/local/bin
`

![captura12](assets/images/nodejs/12.PNG)

Como se puede apreciar en la captura, se ha instalado correctamente.

![captura13](assets/images/nodejs/13.PNG)

Por si hubiera problemas, ejecuto también este comando, que ejecuta paquetes instalados localmente sin necesidad de agregarlos al PATH.


![captura14](assets/images/nodejs/14.PNG)

Y como se puede apreciar, la aplicación se ha iniciado sin problemas.




## Netlify

Primeramente, creamos un directorio con 2 `.html` y un `.js`:

![captura15](assets/images/netlify/1.PNG)

Y, tras comprobar que la aplicación funciona correctamente mediante un `node aplicacion.js`:

![captura16](assets/images/netlify/2.PNG)

![captura17](assets/images/netlify/3.PNG)

*Nota : En el bloque scripts, debemos borrar lo que haya dentro y dejar únicamente dentro de él: "start": "node aplicacion.js", de forma que el sitio donde la despleguemos sepa que comando utilizar para iniciar la aplicación tras desplegarla.*

![captura18](assets/images/netlify/4.PNG)

Clonamos el repositorio indicado en la guía e instalamos el CLI de Netlify.

Tras habernos registrado en Netlify, establecemos el token de autentificación como variable de entorno y nos logueamos:

![captura19](assets/images/netlify/5.PNG)

Instalamos las dependencias y realizamos el build:

![captura20](assets/images/netlify/6.PNG)

![captura21](assets/images/netlify/7.PNG)

Y hacemos el deploy:

![captura22](assets/images/netlify/8.PNG)

![captura23](assets/images/netlify/9.PNG)

Accedemos a esa url y:

![captura24](assets/images/netlify/10.PNG)

¡Aplicación lanzada con éxito!

Para realizar el despliegue mediante GitHub, primero debemos eliminar el sitio:

![captura25](assets/images/netlify/11.PNG)

Eliminamos también el directorio:

![captura26](assets/images/netlify/12.PNG)

Y nos descargamos el siguiente archivo comprimido sin referencias a Github:

![captura27](assets/images/netlify/13.PNG)

![captura28](assets/images/netlify/14.PNG)

Seguimos los siguientes pasos:

![captura29](assets/images/netlify/15.PNG)

![captura30](assets/images/netlify/16.PNG)

![captura31](assets/images/netlify/17.PNG)

En el archivo `robots.txt` escribimos eso:

![captura32](assets/images/netlify/18.PNG)

Y como podemos comprobar se ha desplegado correctamente:

![captura33](assets/images/netlify/19.PNG)

![captura34](assets/images/netlify/20.PNG)

# Fin de la práctica