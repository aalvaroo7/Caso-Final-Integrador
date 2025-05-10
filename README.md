# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git

# Tengo que rehacer lo de las sedes 

# Servicios que ofrece el Ayto. de Coslada a los que hay que implementar un sistema de conexión

![image](https://github.com/user-attachments/assets/cb0bc9ed-2afb-47b4-ac5c-1d4304016382)

Hemos planteado ofrecer una red para cada servicio dividiendo así la red en la red principal (la ubicada En el Ayto. de Coslada) y otras subredes en las cuales se alojarán los distintos servicios, además ofreceremos una propuesta para situar estas redes de forma que no haya que emplear un mayor gasto en 

##  Para ello hemos dividido los servicios según la categoría funcional
##  Para ello hemos dividido los servicios según la categoría funcional
| **Categoría Funcional**                   | **Servicios del Ayuntamiento de Coslada**                                                                 |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 🏛️ **Servicios Gubernamentales**         | - Archivo <br> - Contratación <br> - Economía, Empleo, Comercio, Turismo y Transición Energética <br> - Educación <br> - Hacienda <br> - Participación Ciudadana, Cooperación y Atención a la Ciudadanía <br> - Recursos Humanos <br> - Secretaría General <br> - Urbanismo <br> - Vivienda |
| 🚨 **Seguridad Pública y Emergencias**   | - Seguridad y Emergencias <br> - Salud, Consumo y Bienestar Animal <br> - Igualdad y Diversidad <br> - Mayores <br> - Infancia |
| 🚦 **Transporte y Monitoreo Ambiental**  | - Parques, Jardines y Limpieza Viaria <br> - Transición Ecológica, Movilidad y Transporte <br> - Vías y Obras <br> - Servicios Generales |
| 📺 **Servicios Multimedia para el Ciudadano** | - Cultura <br> - Deportes <br> - Juventud <br> - Servicios Sociales <br> - Informática |

![image](https://github.com/user-attachments/assets/f5626333-aaa4-45ff-80be-8acc8db0bb99)

##  Para cumplir con todo esto hemos planteado dividir la red en varias sedes con varias subredes, en total se ha planteado 4 sedes

![image](https://github.com/user-attachments/assets/497471af-d17f-4cfd-9bbb-e4a6879521ed)

| **Sede**                         | **Servicios Principales Asignados**                                                                                     | **Características Técnicas Clave**                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|  **Sede Central**              | - Comunicación interorganismos<br>- DNS, NTP, AAA<br>- Administración interna<br>- Control de políticas de red          | - Core de ruteo (OSPF)<br>- Firewall perimetral<br>- VPN Gateway/IPSec<br>- ACLs y NAT              |
|  **Sede de Seguridad**         | - Cámaras de videovigilancia<br>- Comunicaciones de emergencia<br>- Salud y Protección Civil                            | - QoS para voz/video<br>- Alta disponibilidad<br>- Red inalámbrica segura<br>- Segmentación IoT     |
|  **Sede de Infraestructura**   | - Semáforos inteligentes<br>- Sensores ambientales (aire, humedad, ruido)<br>- Movilidad urbana                          | - VLANs por tipo de sensor<br>- Protocolo SNMP/MQTT<br>- Enlaces redundantes<br>- Túneles GRE/IPsec |
|  **Sede Ciudadana** | - Streaming de eventos<br>- Kioskos digitales<br>- WiFi ciudadano<br>- Acceso a portales e información pública          | - DMZ protegida<br>- DNSSEC, HTTPS<br>- Captive Portal<br>- Segmentación red pública/interna        |

Notas técnicas
Cada sede tendrá subredes individuales por servicio

La Sede Central dispondrá de:

Firewall/VPN Gateway para acceso remoto seguro.

Enrutador principal con políticas de seguridad (ACL, NAT si aplica).

Conexiones troncales con cada sede usando GRE/IPsec sobre IPv4.

Las demás sedes funcionarán como sucursales LAN conectadas al core central.


# 🛠️ Dispositivos Necesarios en Cisco Packet Tracer

## 🏛️ Sede Central (Hub + Núcleo de red)

| Dispositivo                     | Cantidad | Función                                           |
|--------------------------------|----------|---------------------------------------------------|
| Router ISR4321 o 2901          | 1        | Núcleo de red, VPN/IPSec, OSPF, NAT/ACL          |
| Switch Multicapa (2960 o 3650) | 1–2      | VLANs por servicio, trunk hacia router           |
| PCs o Laptops                  | 5+       | Estaciones administrativas                       |
| Servidores                     | 3–4      | DNS, DHCP, Web, AAA, Streaming                   |
| Firewall (ACL en router)       | -        | Protección de red y DMZ                          |
| Cloud                          | 1        | Simular Internet/transporte IP                   |

---

## 🚨 Sede de Seguridad Pública

| Dispositivo              | Cantidad | Función                                               |
|-------------------------|----------|--------------------------------------------------------|
| Router ISR 2901 o 2811  | 1        | VPN cliente, ruteo local, OSPF                         |
| Switch (2960)           | 1        | VLANs para cámaras, VoIP, PCs                          |
| Cámaras IP              | 2–4      | Vigilancia                                             |
| PCs o Laptops           | 3–4      | Gestión de emergencias                                |
| IP Phones (CP-7960)     | 2–3      | Comunicaciones VoIP                                   |
| Servidor de VoIP        | 1 (opt.) | CME en el router o servidor externo                   |

---

## 🚦 Sede de Infraestructura (IoT y sensores)

| Dispositivo              | Cantidad | Función                                    |
|-------------------------|----------|--------------------------------------------|
| Router ISR 2901 o 2811  | 1        | VPN, OSPF, acceso a sensores               |
| Switch (2960)           | 1        | VLANs por tipo de sensor                   |
| PCs o Laptops           | 2–3      | Gestión de movilidad y SCADA               |
| IoT Devices             | 4–6      | Sensores de humedad, aire, temperatura     |
| Generic Actuators       | 1–2      | Semáforos inteligentes (simulados)         |

---

## 📺 Sede Ciudadana y Multimedia

| Dispositivo                     | Cantidad | Función                                       |
|--------------------------------|----------|-----------------------------------------------|
| Router ISR 2901 o 2811         | 1        | VPN cliente, OSPF, DMZ                        |
| Switch (2960)                  | 1–2      | VLANs para WiFi, streaming, PCs               |
| PCs o Laptops                  | 4–6      | Kioskos digitales, terminales ciudadanas      |
| Servidor Web / Streaming       | 1–2      | Servicios web y multimedia                    |
| Access Point (Linksys / Gen.)  | 1–2      | Red WiFi para usuarios                        |
| Firewall (ACL en router)       | -        | Separación red pública/privada                |

---

## 🔌 Conectividad Global

| Elemento                        | Cantidad      | Función                                          |
|--------------------------------|---------------|--------------------------------------------------|
| Cables (cobre, fibra, consola) | Según diseño  | Conexiones entre dispositivos                    |
| Túneles GRE/IPsec (config)     | 3             | Entre cada sede remota y la central              |
| Direcciones IP/VLAN            | Según sede    | Plan de direccionamiento estructurado            |


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

