# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git

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


