# Practica 3.3
# Despliegue de una aplicación Flask (Python)

## Procedimiento completo para el despliegue

Lo primero que tenemos que hacer es instalar el gestor de paquetes de Python `pip`:

![captura1](assets/images/1.PNG)
![captura2](assets/images/2.PNG)
![captura3](assets/images/3.PNG)

Creamos un directorio donde almacenaremos la aplicación y le establecemos los permisos necesarios:

![captura4](assets/images/4.PNG)
![captura5](assets/images/5.PNG)

Creamos un archivo oculto con las variables de entorno necesarias:

![captura6](assets/images/6.PNG)

E iniciamos el entorno virtual:

![captura7](assets/images/7.PNG)

Instalamos las dependencias necesarias para este proyecto en concreto:

![captura8](assets/images/8.PNG)

Creamos los siguientes archivo, de manera que se vea tal que así:

![captura9](assets/images/9.PNG)
![captura10](assets/images/10.PNG)
![captura11](assets/images/11.PNG)
![captura12](assets/images/12.PNG)

Y corremos nuestra aplicación:

![captura13](assets/images/13.PNG)

Debemos comprobar que funciona accediendo a nuestra dirección IP en el navegador.

![captura14](assets/images/14.PNG)

Y como se puede apreciar, la aplicación se ha iniciado sin problemas.

Para parar el servidor pulsamos CTRL + C.

Ahora bien, para comprobar que Gunicorn funciona correctamente introducimos el siguiente comando:

![captura15](assets/images/15.PNG)

Y tomamos nota de la ruta desde la que se ejecuta.

![captura16](assets/images/16.PNG)

Para salir del entorno virtual tenemos que introducir `deactivate`:

![captura17](assets/images/17.PNG)

Tras esto, tenemos que asegurarnos que Nginx está funcionando.

![captura18](assets/images/18.PNG)

Y crear un archivo para que `systemd` corra Gunicorn:

![captura19](assets/images/19.PNG)
![captura20](assets/images/20.PNG)

Ahora habilitamos e iniciamos el servicio:

![captura21](assets/images/21.PNG)

Para el siguiente paso tendremos que configurar Nginx. Editamos el archivo de la aplicación en `sites-available` de manera que se vea así:

![captura22](assets/images/22.PNG)
![captura23](assets/images/26.PNG)

Y creamos nuestro enlace simbólico:

![captura24](assets/images/24.PNG)
![captura25](assets/images/25.PNG)

Tras esto, nos aseguramos de que hemos configurado Nginx correctamente y reiniciamos el servicio:

![captura26](assets/images/27.PNG)

Modificaremos el archivo `/etc/hosts`:

![captura27](assets/images/29.PNG)
![captura28](assets/images/28.PNG)

Como hemos realizado todos los pasos correctamente, al comprobar si la aplicación se ha desplegado de manera exitosa veremos que, en efecto, así es:

![captura29](assets/images/30.PNG)

## Realizar el mismo procedimiento con la aplicación clonada del repositorio

Ahora tenemos que realizar todo este proceso pero con la aplicación que se nos proporciona en el GitHub de la guía, por lo que clonamos el repositorio y procedemos a hacer lo mismo:

![captura30](assets/images/31.PNG)

1. Creamos el archivo oculto:

![captura31](assets/images/32.PNG)

2. Otorgamos los permisos necesarios:

![captura32](assets/images/33.PNG)

3. Iniciamos el entorno virtual:

![captura33](assets/images/35.PNG)

4. Comprobamos que la aplicación se despliega correctamente:

![captura34](assets/images/36.PNG)

5. Comprobamos que Gunicorn funciona correctamente:

![captura35](assets/images/37.PNG)

6. Tomamos nota de la ruta:

![captura36](assets/images/38.PNG)

7. Creamos el archivo para `systemd`:

![captura37](assets/images/41.PNG)

8. Modificamos la configuración de Nginx:

![captura38](assets/images/42.PNG)

9. Habilitamos el servicio:

![captura39](assets/images/43.PNG)

10. Y para terminar, creamos el enlace simbólico y modificamos `/etc/hosts`:

![captura40](assets/images/44.PNG)
![captura41](assets/images/45.PNG)

# Cuestiones

>Busca, lee, entiende y explica qué es y para que sirve un servidor WSGI

Un servidor WSGI (Web Server Gateway Interface) actúa como intermediario entre aplicaciones web escritas en Python y servidores web como Apache o Nginx, traduciendo solicitudes HTTP en datos procesables por Python y devolviendo respuestas al cliente. Permite compatibilidad entre frameworks, facilita el despliegue en producción y mejora el manejo de múltiples solicitudes concurrentes de manera eficiente