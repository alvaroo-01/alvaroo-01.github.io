# Practica 4.1
# Instalación de un servidor DNS

Tenemos que escribir el siguiente comando:

![captura1](assets/images/1.PNG)

## Configuración del servidor

Tendremos que modificar el archivo ```/etc/default/named```

![captura2](assets/images/2.PNG)

![captura3](assets/images/3.PNG)

En ```OPTIONS=``` escribimos lo siguiente:

![captura4](assets/images/4.PNG)

Una vez hecho esto, podemos instalar nodejs:

![captura5](assets/images/5.PNG)

Aquí podemos encontrar los 3 archivos que vamos a modificar a lo largo de la práctica.

![captura6](assets/images/6.PNG)

Realizamos una copia del archivo ```named.conf.options```:

![captura7](assets/images/7.PNG)

Y ya podemos modificar el archivo sin miedo.

Antes de options escribimos lo siguiente, rellenándolo con nuestra ip propia.

![captura8](assets/images/8.PNG)

![captura11](assets/images/11.PNG)
*Nota: esa es mi IP*

Y tras forwarded ponemos las siguientes opciones:

![captura10](assets/images/10.PNG)

Podemos comprobar que hasta ahora todo funciona correctamente con el siguiente comando:

![captura12](assets/images/12.PNG)

Y ahora reiniciamos el servicio y comprobamos el estado:

![captura13](assets/images/13.PNG)

Ahora debemos modificar el archivo ```/etc/bind/named.conf.local```

![captura14](assets/images/14.PNG)

## Creación del archivo de zona (resolución directa e inversa)

En la captura se muestra como se crea la zona, ahora sólo necesitamos el archivo de zona.

El nombre del archivo será ```db.deaw.es```, que es el nombre que le hemos dado a la zona en ```/etc/bind/named.conf.local```.

![captura15](assets/images/15.PNG)
*Nota: se le puede dar cualquier valor numérico al serial, aunque se recomienda usar el año, mes, día y versión*.

Debemos crear un archivo de zona para la resolución inversa, pero antes creamos la zona en ```/etc/bind/named.conf.local```.

![captura16](assets/images/16.PNG)

![captura17](assets/images/17.PNG)
*en mi caso lo llamaré ```db.115.168.192``` porque es mi dirección IP inversa sin contar el último byte.*

## Comprobación de las configuraciones

Comprobamos que tanto la resolución directa e inversa se han configurado correctamente con el siguiente comando:

![captura18](assets/images/18.PNG)

Y reiniciamos el servicio de nuevo:

![captura19](assets/images/19.PNG)

Abrimos otra máquina virtual a modo de cliente (o lo hacemos desde nuestra propia máquina) y creamos el siguiente archivo de configuración:

![captura20](assets/images/20.PNG)
*Nota: En nameserver ponemos nuestra dirección IP correspondiente*

Introducimos los siguientes comandos:

![captura21](assets/images/21.PNG)


![captura22](assets/images/22.PNG)

Como se puede comprobar, funciona todo correctamente.

## Cuestiones Finales

### Cuestión 1
**¿Qué pasará si un cliente de una red diferente a la tuya intenta hacer uso de tu DNS de alguna manera, le funcionará?¿Por qué, en qué parte de la configuración puede verse?**

No funcionará, ya que en la configuración se ha indicado: ```allow-recursion{confiables;};```

### Cuestión 2
**¿Por qué tenemos que permitir las consultas recursivas en la configuración?**

Porque sin recursión no resolvería nombres externos.

### Cuestión 3
**El servidor DNS que acabáis de montar, ¿es autoritativo?¿Por qué?**

Sí, se ha introducido ```type master;``` y recibe registros DNS de una sola zona específica.

### Cuestión 4
**¿Dónde podemos encontrar la directiva $ORIGIN y para qué sirve?**

En los archivos de zona. Establece el dominio base para los registros.

### Cuestión 5
**¿Una zona es idéntico a un dominio?**

No, un dominio es un nombre dentro del sistema DNS. Una zona es una parte de un dominio gestionada por un servidor DNS específico.

### Cuestión 6
**¿Pueden editarse los archivos de zona de un servidor esclavo/secundario?**

No, los servidores secundarios obtienen los datos de un servidor maestro mediante transferencias de zona.

### Cuestión 7
**¿Por qué podría querer tener más de un servidor esclavo para una misma zona?**

Para mejorar la redundancia y la disponibilidad. Si un servidor secundario falla, los otros servidores secundarios pueden seguir respondiendo a las consultas.

### Cuestión 8
**¿Cuántos servidores raíz existen?**

Existen 13 servidores raíz.

### Cuestión 9
**¿Qué es una consulta iterativa de referencia?**

Una consulta en la que un servidor DNS responde con la mejor información que tiene.

### Cuestión 10
**En una resolución inversa, ¿a qué nombre se mapearía la dirección IP 172.16.34.56?**

56 IN PTR + [nombre_host].