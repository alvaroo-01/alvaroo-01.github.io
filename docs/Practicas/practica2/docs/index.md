# Practica 2

## Instalación del servidor web Nginx

Lo primero es lo primero, hay que actualizar, por lo que usamos ```sudo apt update``` y una vez hecho eso, instalamos NGinx mediante ```sudo apt install nginx```

![captura1](assets/images/1.PNG)

Podemos comprobar que todo está en orden así:

![captura2](/docs/assets/images/2.PNG)

## Creación del directorio

Una vez hecho esto, nos creamos nuestro directorio:

![captura3](/docs/assets/images/3.PNG)

*Nota: Al comprobar que la web funcionaba correctamente con http y https caí en la cuenta de que el dominio www.alvaro.com ya estaba en uso, por lo que puede que en las capturas el nombre del directorio esté cambiado de:*

`alvaro -> alvaro_web_imposiblequeestepillado`

Ahora tenemos que clonar el repositorio que aparece en la guía, asíque necesitamos tener instalado git.

![captura4](/docs/assets/images/4.PNG)

Y ahora sí, clonamos el repositorio y nos damos permiso:

![captura5](/docs/assets/images/5.PNG)
![copia](/docs/assets/images/18.PNG)
![captura6](/docs/assets/images/19.PNG)

Podemos comprobar que hasta ahora va todo bien si en el navegador introducimos la ip de la máquina y sale lo siguiente:

![captura7](/docs/assets/images/6.PNG)

## Configuración del servidor

Necesitamos editar el siguiente archivo:

![captura8](/docs/assets/images/7.PNG)

E introducimos esto:

![captura9](/docs/assets/images/8.PNG)

![captura10](/docs/assets/images/9.PNG)

## Comprobaciones

Ahora en nuestra máquina física debemos modificar el archivo hosts, en mi caso (Windows) en `System32\drivers\etc\hosts`.

![captura11](/docs/assets/images/10.PNG)

*Nota: El puerto indicado no es el correcto, solo lo puse a modo de placeholder, puesto que al estar cambiando de ubicación constantemente (instituto y mi lugar de residencia) no introduje la correcta. El nombre web por otra parte, como se ha indicado anteriormente, tampoco es el definitivo.*

## FTP

Ahora toca la parte de FTP:

![captura12](/docs/assets/images/11.PNG)
![captura13](/docs/assets/images/12.PNG)

Y en el archivo `/etc/vsftpd.conf` buscamos esto:

![captura14](/docs/assets/images/13.PNG)

Y lo cambiamos por esto:

![captura15](/docs/assets/images/14.PNG)

![captura16](/docs/assets/images/15.PNG)

Ahora tendremos que instalar el cliente de FileZilla en nuestra máquina física para realizar la prueba.

![captura17](/docs/assets/images/16.PNG)

*Nota: Me he conectado por el puerto 22*

![captura18](/docs/assets/images/17.PNG)

Hacemos click derecho en cualquier archivo que queramos subir (en mi caso, la carpeta *despliegue*) y nos dejará subirla sin ningún problema.

## HTTPS

Para el apartado de HTTPS, tenemos que modificar `sites-enabled`:

![captura19](/docs/assets/images/20.PNG)

Nos damos permisos y reiniciamos:

![captura20](/docs/assets/images/21.PNG)

Y como podemos comprobar, funciona:

![captura21](/docs/assets/images/22.PNG)

*Nota: En mi caso, no borro el directorio html porque tengo el root en ese directorio.*