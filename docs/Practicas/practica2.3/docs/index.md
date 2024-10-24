# Practica 2.3
# Proxy inverso con Nginx

## Configuraciones

Primero tenemos que clonar nuestra máquina con el servidor Nginx y generar nuevas MACs:

![captura1](assets/images/1.PNG)

![captura2](assets/images/2.PNG)

Una vez clonada, en la máquina del servidor cambiamos el nombre de nuestro dominio por webserver y que escuche por el puerto 8080.

![captura3](assets/images/3.PNG)

![adicional](assets/images/7.PNG)

![captura4](assets/images/4.PNG)

Y borramos el link simbólico:

![captura5](assets/images/5.PNG)


Y creamos el nuevo:

![captura6](assets/images/6.PNG)

Reiniciamos Nginx:

![captura7](assets/images/8.PNG)

Y en la máquina proxy creamos un archivo de configuración que quede tal que así:

![captura8](assets/images/12.PNG)

De nuevo, creamos el link simbólico:

![captura11](assets/images/10.PNG)

Y en nuestra máquina anfitriona agregamos al hosts lo siguiente:

![captura12](assets/images/16.PNG)

![captura13](assets/images/12.PNG)

## Comprobaciones

Añadimos cabeceras tanto en el servidor como en el proxy:

![captura14](assets/images/13.PNG)


![captura15](assets/images/14.PNG)

Y si utilizamos las herramientas de desarrollador de Google Chrome podemos comprobar que las cabeceras añadidas previamente se hallan ahí.

![captura16](assets/images/15.PNG)
