# Practica 2.4
# Balanceo de carga con proxy inverso en NGinx

## Configuraciones

Primero tenemos que clonar nuestra máquina y generar nuevas MACs:

### Servidor Nginx 1

![captura1](assets/images/1.PNG)

Lo primero que deberemos hacer es cargarnos el enlace simbólico. Repetiremos el mismo proceso en la segunda máquina.

![captura2](assets/images/2.PNG)

![captura3](assets/images/3.PNG)
*Cambio de nombre*

Debemos cargarnos el sitio web con el que hemos estado trabajando hasta ahora y crear un index nuevo.

![captura4](assets/images/4.PNG)


El index del webserver1:

![captura5](assets/images/5.PNG)

Y creamos el nuevo enlace simbólico:

![captura6](assets/images/6.PNG)

Y creamos el nuevo archivo de configuración:

![captura7](assets/images/7.PNG)


### Servidor Nginx 2

Nos cargamos el enlace simbólico de la anterior máquina:

![captura8](assets/images/8.PNG)

Renombramos de nuevo el sitio web...

![captura11](assets/images/10.PNG)

Y repetimos el archivo de configuración, cambiando cualquier alusión a webserver1 por webserver2.

![captura13](assets/images/12.PNG)

Y creamos el enlace simbólico.

![captura14](assets/images/13.PNG)

### Proxy inverso

Finalmente, en sites-available, creamos un nuevo archivo de configuración:

![captura15](assets/images/14.PNG)


### Cuestiones finales

1. Busca información de qué otros métodos de balanceo se pueden aplicar con Nginx y describe al menos 3 de ellos.

 - Round Robin:

Este es el método predeterminado en Nginx si no se especifica otro. Las solicitudes se distribuyen en turnos entre los servidores disponibles, sin tener en cuenta la carga actual ni la capacidad de cada servidor. Este método es simple y efectivo cuando los servidores tienen capacidades similares.

Configuración básica:
`upstream backend {
    server backend1.example.com;
    server backend2.example.com;
    server backend3.example.com;
}
`

 - Least Connections:

Con el método de "least connections" (menor número de conexiones), Nginx dirige cada solicitud al servidor con menos conexiones activas en ese momento. Esto ayuda a distribuir las cargas de manera más uniforme cuando algunos servidores están temporalmente más ocupados que otros.

Configuración básica:
`upstream backend {
    least_conn;
    server backend1.example.com;
    server backend2.example.com;
    server backend3.example.com;
}`

 - IP Hash:

En este método, Nginx asigna las solicitudes a un servidor específico en función de la dirección IP del cliente. Esto garantiza que un cliente con la misma IP siempre se conecte al mismo servidor, útil para mantener la sesión de usuario en aplicaciones que no son "stateless" o que requieren persistencia en el servidor.

Configuración básica:
`upstream backend {
    ip_hash;
    server backend1.example.com;
    server backend2.example.com;
}`

2. Si quiero añadir 2 servidores web más al balanceo de carga, describe detalladamente qué configuración habría que añadir y dónde.

Primero, debes ubicar la configuración del bloque upstream en el archivo de configuración de Nginx, que generalmente se encuentra en /etc/nginx/nginx.conf o en un archivo separado en el directorio /etc/nginx/conf.d/ (según cómo esté configurado tu servidor).

Dentro de este bloque, define los servidores existentes y agrega los nuevos servidores adicionales.


Asegúrate de que el bloque server correspondiente esté configurado para usar el bloque upstream. Esto suele estar en el archivo de configuración de tu host virtual, ubicado en /etc/nginx/sites-available/ o /etc/nginx/sites-enabled/, o también en /etc/nginx/nginx.conf si la configuración es global.

Finalmente, aplica los cambios recargando o reiniciando el servicio Nginx.