# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git

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
| `switchport access vlan 10`  | Asignación de los puertos a la VLAN 10            |
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
