+++
author = "Hugo Authors"
title = "Mermaid"
date = "2022-23-10"
description = "Proceso de carga en un servidor "
tags = [
    "Mermaid",
    "privacy",
]
+++

Cuando nosotros queremos ver una página web, nosotros lo que hacemos es poner la dirección de esta en nuestro navegador, esperamos un par de segundos y esta como por arte de magia carga, pero… ¿Sabes realmente que es lo que hace de fondo el navegador?

Terminos a conocer
Las IPs, las matriculas de internet
Por si no lo sabías, los ordenadores internamente no funcionan con nombres de dominio (conocidos generalmente de forma incorrecta como URLs) sino que usan varios típos de identificadores, uno de ellos son las IPs.

Una IP se utiliza para conectar con un equipo en red, y de esta forma poder obtener recursos en el y/o enviarselos.

Las IPs en los sistemas domésticos las suele asignar el router, mediante un servidor interno conocido como DHCP.

Este lo que hace es cuando tu te conectas a la red, ya sea por wifi o por cable elige un numero dentro del rango que le tenemos asignado que no este usando ningun equipo más en la red. En un sistema casero suele ser una ip dentro del rango generalmente 192.168.1.[0-255]

El servidor DNS, el diccionario de las webs
Como he explicado anteriormente intenet funciona por IPs, por lo tanto es necesario de alguna forma “convertir” una URL como google.es en una ip como 142.250.185.3

El proceso de carga
PC CLIENTE introduce la URI del servidor que quiere visitar

PC CLIENTE manda solicitud al NAT del ROUTER CLIENTE

ROUTER CLIENTE hace NAT y realiza una solicitud al SERVIDOR DNS que esta configurado

SERVIDOR DNS busca en los registros y si no lo encuentra en sus registros, escala la solicitud a servidores DNS primarios hasta encontrarlo

El SERVIDOR DNS se encarga de devolver el registro al ROUTER CLIENTE (Este registro ha podido ser encontrado en el mismo servidor o puede ser el que le han devuelto los otros servidores DNS).

Se devuelve el registro al ROUTER CLIENTE.

El ROUTER CLIENTE realiza el NAT y se lo devuelve al PC CLIENTE.

El PC CLIENTE realiza la solicitud a la IP, que le ha devuelto el Servidor DNS, correspondiente al servidor del recurso solicitado.

Se vuelve a mandar la solicitud al ROUTER CLIENTE que vuelve a hacer NAT.

El ROUTER CLIENTE realiza la solicitud al SERVIDOR WEB.

El SERVIDOR atiende a la solicitud mediante el siguiente orden de prioridad:

{{<mermaid align="left">}}
graph LR;
    A[Cliente] --> B(Dominio)
    B --> C(Puerto)
    C --> D(Ruta)
    D --> E(Parametros)
{{< /mermaid >}}

En caso de carga de pagina web por ejemplo al ver el protocolo http/https se mandará la petición al servicio apache2/nginx instalados en SERVIDOR, que son los que procesarán el resto de la petición.

El servidor devuelve el recurso solicitado al ROUTER CLIENTE

El ROUTER CLIENTE vuelve a realizar NAT

El ROUTER CLIENTE devuelve la petición al PC CLIENTE
