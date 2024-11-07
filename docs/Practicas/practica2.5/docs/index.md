# Practica 2.5
# Proxy inverso y balanceo de carga con SSL en NGINX

Partiendo de la práctica anterior...

## Creación de certificado autofirmado

Lo primero que tenemos que hacer es crear el siguiente directorio:

![captura1](assets/images/1.PNG)

Y utilizar el siguiente comando, con el que crearemos el certificado y las claves de forma simultánea:
![captura2](assets/images/2.PNG)

*Nota:La práctica dice que se introduzcan exactamente los datos que aparecen en pantalla. Por asegurarme, así lo he hecho.*

![captura3](assets/images/3.PNG)
*Cambio de nombre*

## Configuración SSL en el proxy inverso

En el archivo de configuración `/etc/nginx/sites-available/balanceo` debemos indicar que escuche por el puerto 443:

![captura4](assets/images/4.PNG)


## Comprobaciones

Con nuestras otras dos máquinas encendidas, al intentar acceder desde nuestra máquina local a https:balanceo se nos pedirá autenticarnos:

![captura5](assets/images/5.PNG)
![captura6](assets/images/6.PNG)
![captura7](assets/images/7.PNG)

Y si vemos el certificado, comprobamos que está todo en orden:

![captura8](assets/images/8.PNG)