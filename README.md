# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git


## Información sobre el protocolo usado y su predecesor 

# 📋 EIGRP - Características, Ventajas y Desventajas

## 🔧 Características de EIGRP

| Característica                            | Descripción                                                                 |
|-------------------------------------------|-----------------------------------------------------------------------------|
| Tipo de protocolo                         | Híbrido (Vector distancia + Estado de enlace)                              |
| Algoritmo de enrutamiento                 | DUAL (Diffusing Update Algorithm)                                          |
| Métrica                                   | Basada en ancho de banda, retardo, carga y confiabilidad                   |
| Transporte                                | RTP (Reliable Transport Protocol)                                          |
| Soporte de protocolos                     | IPv4 e IPv6                                                                |
| Soporte de VLSM y CIDR                    | ✅ Sí                                                                       |
| Balanceo de carga                         | ✅ Sí (igual y desigual)                                                   |
| Rutas de respaldo                         | ✅ Feasible successors                                                     |
| Tipo de actualizaciones                   | Parciales y triggered (no periódicas)                                     |
| Detección de bucles                       | ✅ Muy eficiente (gracias a DUAL)                                          |

---

## ✅ Ventajas de EIGRP

| Ventaja                                | Descripción                                                                 |
|----------------------------------------|-----------------------------------------------------------------------------|
| Convergencia rápida                    | DUAL permite encontrar nuevas rutas rápidamente                            |
| Uso eficiente del ancho de banda       | Solo envía actualizaciones cuando hay cambios                              |
| Alta escalabilidad                     | Ideal para redes grandes                                                   |
| Soporte de múltiples protocolos        | Compatible con IPv4, IPv6 y protocolos antiguos (como IPX, AppleTalk)      |
| Balanceo de carga desigual             | Permite usar rutas con diferente métrica                                   |
| Rutas de respaldo inmediatas           | No es necesario recalcular todo cuando una ruta falla                      |

---

## ⚠️ Desventajas de EIGRP

| Desventaja                             | Descripción                                                                 |
|----------------------------------------|-----------------------------------------------------------------------------|
| Propietario de Cisco (parcialmente)   | Aunque fue parcialmente abierto, no todos los fabricantes lo soportan      |
| Menos estandarizado que OSPF          | Puede generar problemas en entornos mixtos (no Cisco)                      |
| Complejidad relativa                  | Más complejo de configurar que RIP para redes pequeñas                     |

# Comparación entre IGRP y EIGRP

| Característica                   | IGRP (Interior Gateway Routing Protocol) | EIGRP (Enhanced Interior Gateway Routing Protocol) |
|----------------------------------|------------------------------------------|-----------------------------------------------------|
| **Desarrollado por**             | Cisco                                    | Cisco                                               |
| **Tipo de protocolo**            | Vector distancia                         | Híbrido (vector distancia + estado de enlace)       |
| **Algoritmo de enrutamiento**    | Vector distancia clásico                 | DUAL (Diffusing Update Algorithm)                   |
| **Métrica utilizada**            | Ancho de banda, retardo, carga, fiabilidad | Ancho de banda, retardo, carga, fiabilidad         |
| **Velocidad de convergencia**    | Lenta                                    | Rápida                                              |
| **Soporta VLSM/CIDR**            | ❌ No                                     | ✅ Sí                                                |
| **Soporta IPv6**                 | ❌ No                                     | ✅ Sí                                                |
| **Balanceo de carga desigual**   | ❌ No                                     | ✅ Sí                                                |
| **Rutas de respaldo (feasible successors)** | ❌ No                     | ✅ Sí                                                |
| **Protocolos de transporte**     | Sin protocolo específico                 | RTP (Reliable Transport Protocol)                   |
| **Manejo de bucles**             | Deficiente                               | Excelente (mediante DUAL)                           |
| **Estado actual**                | Obsoleto                                 | En uso (principalmente en entornos Cisco)           |
| **Abierto/Propietario**          | Propietario                              | Inicialmente propietario, luego parcialmente abierto|

## Comandos usados para la red básica para configurar un EIGRP (simple)

Pasos de configuración
📍 Supuestos de direccionamiento
Segmento	VLAN	Dirección IP Router	Red
LAN Izquierda (Router5)	10	192.168.10.1	192.168.10.0/24
LAN Derecha (Router6)	20	192.168.20.1	192.168.20.0/24
Enlace entre routers	—	192.168.100.1 / .2	192.168.100.0/30

Configuración de Router5

| **Comando**                                | **Descripción**                                    |
| ------------------------------------------ | -------------------------------------------------- |
| `interface g0/0.10`                        | Subinterfaz para VLAN 10                           |
| `encapsulation dot1Q 10`                   | Configuración de encapsulación 802.1Q para VLAN 10 |
| `ip address 192.168.10.1 255.255.255.0`    | Dirección IP de la subinterfaz                     |
| `no shutdown`                              | Activación de la interfaz                          |
| `interface g0/1`                           | Enlace hacia Router6                               |
| `ip address 192.168.100.1 255.255.255.252` | Dirección IP del enlace hacia Router6              |
| `no shutdown`                              | Activación de la interfaz                          |
| `router eigrp 1`                           | Configuración de EIGRP                             |
| `network 192.168.10.0`                     | Red de la subinterfaz VLAN 10                      |
| `network 192.168.100.0`                    | Red del enlace hacia Router6                       |
| `no auto-summary`                          | Desactivación de auto-sumarización                 |


Configuración de Router6

| **Comando**                                | **Descripción**                                    |
| ------------------------------------------ | -------------------------------------------------- |
| `interface g0/0.20`                        | Subinterfaz para VLAN 20                           |
| `encapsulation dot1Q 20`                   | Configuración de encapsulación 802.1Q para VLAN 20 |
| `ip address 192.168.20.1 255.255.255.0`    | Dirección IP de la subinterfaz                     |
| `no shutdown`                              | Activación de la interfaz                          |
| `interface g0/1`                           | Enlace hacia Router5                               |
| `ip address 192.168.100.2 255.255.255.252` | Dirección IP del enlace hacia Router5              |
| `no shutdown`                              | Activación de la interfaz                          |
| `router eigrp 1`                           | Configuración de EIGRP                             |
| `network 192.168.20.0`                     | Red de la subinterfaz VLAN 20                      |
| `network 192.168.100.0`                    | Red del enlace hacia Router5                       |
| `no auto-summary`                          | Desactivación de auto-sumarización                 |


Configuración de los Switches

| **Comando**                  | **Descripción**                                   |
| ---------------------------- | ------------------------------------------------- |
| `interface range fa0/1 - 24` | Configuración del rango de puertos de acceso      |
| `switchport mode access`     | Configuración de puertos como puertos de acceso   |
| `switchport access vlan n !La que sea`  | Asignación de los puertos a la VLAN 10            |
| `spanning-tree portfast`     | Activación de PortFast para evitar retardo de STP |
| `interface fa0/x`            | Configuración del puerto troncal hacia el router  |
| `switchport mode trunk`      | Configuración de puerto como troncal              |

💻 Configuración de los PCs
PC	IP	Gateway
PC2/PC3	192.168.10.X	192.168.10.1
PC4/PC5	192.168.20.X	192.168.20.1

✅ Comprobaciones
ping desde PC2 a PC4

show ip route en ambos routers para ver que aprendieron rutas con EIGRP

show ip protocols para confirmar EIGRP activo

# Enlaces útiles

https://www.cisco.com/en/US/docs/ios/lanswitch/configuration/guide/lsw_cfg_vlan_encap.html?utm_source=chatgpt.com

https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_eigrp/configuration/15-mt/ire-15-mt-book/ire-enhanced-igrp.html?utm_source=chatgpt.com
