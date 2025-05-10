# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git


# Topología a usar

![image](https://github.com/user-attachments/assets/ae5fb8db-748f-4a03-93ef-f8a71eaef8a9)

# A implementar 

--> Dispositivos IOT con su debido server 

--> VPN + ACLS + IPSEC <-- Todo en uno 

--> Modificar la web (si se puede)

# VPN
https://www.cisco.com/c/en/us/solutions/small-business/resource-center/security/how-to-setup-a-vpn.html

## Links a videos interesantes sobre tunelado, vpn e ipsec

https://www.youtube.com/watch?v=CsAROSbZF-Y&list=PLvUOx2WG6R7N5mUWwB-_YLWEkk491XqKx&index=62&t=315s <--- Montado de una vpn con ipsec(encriptación)

https://www.youtube.com/watch?v=OQVKp6VLyls&t=127s <--- Tunnelado de ipv6 SOBRE ipv4

https://www.youtube.com/watch?v=hY1sXBt-CQY&list=PLvUOx2WG6R7N5mUWwB-_YLWEkk491XqKx <-- Enlace curso completo del CCNA

https://www.cisco.com/c/en/us/support/docs/ip/ip-version-6/25156-ipv6tunnel.html#:~:text=This%20document%20provides%20a%20sample,the%20IPv4%20backbone%20that%20exists




## COMO CONFIGURAR LOS SERVIDORES DE FTP DE UN SERVIDOR 

https://netizzan.com/how-to-configure-tftp-server-in-packet-tracer

https://mediateca.educa.madrid.org/video/qqz61biyuiak3w68

https://informatica.uv.es/~carlos/docencia/netinvm/es/netinvm-intro/netinvm-intro.html


Para lo de informatica de uv tenemos que hacer hasta la parte 18

https://informatica.uv.es/~carlos/docencia/netinvm/es/netinvm-intro/netinvm-intro.html

### Opcional 

https://link.springer.com/article/10.1007/s10586-024-04291-z


https://tuto-mundo.blogspot.com/2012/11/configuracion-de-servidor-http-dhcp.html


## Info sobre los tipos de enrutamiento y los tipos de ip

## Tipos de enrutamiento dinámico

| **Protocolo** | **Tipo**                                            | **Uso principal**                                                     | **Ventajas**                                                     | **Desventajas**                                                          |
| ------------- | --------------------------------------------------- | --------------------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **RIP v2**    | Vector de distancia                                 | Redes pequeñas con poca complejidad                                   | Fácil de configurar, admite VLSM (en v2)                         | Lento en converger, límite de 15 saltos                                  |
| **EIGRP**     | Vector de distancia avanzado (propietario de Cisco) | Redes medianas a grandes dentro de entornos Cisco                     | Rápida convergencia, eficiente, admite VLSM, métricas compuestas | Solo funciona en equipos Cisco (aunque hay una versión limitada abierta) |
| **OSPF**      | Estado de enlace                                    | Redes medianas a grandes, interoperables entre diferentes fabricantes | Convergencia rápida, escalabilidad, admite múltiples áreas, VLSM | Más complejo de configurar que RIP/EIGRP                                 |
| **BGP**       | Vector de ruta (Path vector)                        | Interconexión entre organizaciones o ISPs (Internet)                  | Escalable globalmente, controla rutas entre AS                   | Muy complejo, requiere mucho conocimiento técnico                        |

## Tipos de enrutamiento según la función que desarrollan en cisco paquet tracer

| **Protocolo** | **Tipo**                             | **Uso dentro de Cisco Packet Tracer**                                             | **Ventajas en Packet Tracer**                                                  | **Limitaciones dentro del simulador**                                             |
| ------------- | ------------------------------------ | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| **RIP v2**    | Vector de distancia                  | Ideal para practicar conceptos básicos de enrutamiento dinámico                   | Fácil de configurar, útil para aprender subnetting y saltos                    | No soporta rutas más allá de 15 saltos, convergencia lenta                        |
| **EIGRP**     | Vector de distancia avanzado (Cisco) | Muy útil para prácticas con múltiples redes, métrica compuesta, resumen de rutas  | Admite VLSM, rápida convergencia, buenas métricas, ideal para topologías Cisco | Solo funciona entre routers Cisco, configuración más extensa que RIP              |
| **OSPF**      | Estado de enlace                     | Muy útil para redes jerárquicas (multiárea), interoperabilidad entre dispositivos | Potente en topologías grandes, buen soporte en Packet Tracer                   | Configuración más detallada (áreas, ID de router, máscaras wildcard)              |
| **BGP**       | Vector de ruta (Path vector)         | *No soportado* en Cisco Packet Tracer                                             | N/A                                                                            | **No disponible** en Packet Tracer, solo en simuladores más avanzados (GNS3, CML) |

Para la topología empleada usaremos el protocolo de enrutamiento dinámico EIGRP, debido a los siguientes motivos:

Excelente para topologías tipo hub-and-spoke , como en la topología propuesta en la cual la central es el hub 

Soporta resumen de rutas en la sede central por lo tanto aporta escalabilidad

Tiene rápida convergencia y es más estable que RIP.

Es fácil de configurar comparado con OSPF 

# Tipos de ip y sus usos

| **Clase de IP** | **Rango de direcciones**    | **Máscara de subred por defecto** | **Rango de direcciones utilizables** | **Número de direcciones** | **Uso típico**                                         | **Impacto en la conexión**                                                                                                                                               |
| --------------- | --------------------------- | --------------------------------- | ------------------------------------ | ------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Clase A**     | 0.0.0.0 - 127.255.255.255   | 255.0.0.0                         | 1.0.0.1 - 127.255.255.254            | 16,777,216                | Redes grandes (ISPs, grandes empresas)                 | Permite redes muy grandes y la expansión sin problemas. Puede ser difícil de gestionar debido al alto número de direcciones y la necesidad de segmentar subredes.        |
| **Clase B**     | 128.0.0.0 - 191.255.255.255 | 255.255.0.0                       | 128.0.0.1 - 191.255.255.254          | 65,536                    | Redes medianas (universidades, empresas grandes)       | Ideal para redes de tamaño medio. Requiere una gestión eficiente, pero ofrece un buen balance entre direcciones disponibles y facilidad de gestión.                      |
| **Clase C**     | 192.0.0.0 - 223.255.255.255 | 255.255.255.0                     | 192.0.0.1 - 223.255.255.254          | 256                       | Redes pequeñas (hogares, pequeñas empresas)            | Adecuado para redes pequeñas. La cantidad limitada de direcciones hace que sea fácil de gestionar, pero puede ser un problema si se necesita más espacio de direcciones. |
| **Clase D**     | 224.0.0.0 - 239.255.255.255 | No aplica                         | Direcciones para multidifusión       | No tiene límite definido  | Multidifusión (transmisiones a múltiples dispositivos) | Utilizada para aplicaciones de difusión de datos a varios dispositivos a la vez (multicast). No se utiliza para redes estándar.                                          |
| **Clase E**     | 240.0.0.0 - 255.255.255.255 | No aplica                         | Reservado para uso experimental      | No tiene límite definido  | Uso experimental                                       | Reservada para usos experimentales y futuros, no se utiliza en redes públicas.                                                                                           |


