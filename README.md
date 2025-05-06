# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git

## Comandos usados para la red básica para configurar un EIGRP (simple)

Pasos de configuración
📍 Supuestos de direccionamiento
Segmento	VLAN	Dirección IP Router	Red
LAN Izquierda (Router5)	10	192.168.10.1	192.168.10.0/24
LAN Derecha (Router6)	20	192.168.20.1	192.168.20.0/24
Enlace entre routers	—	192.168.100.1 / .2	192.168.100.0/30

🔧 Configuración de Router5
bash
Copiar
Editar
! Subinterfaz para VLAN 10
interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
 no shutdown

! Enlace hacia Router6
interface g0/1
 ip address 192.168.100.1 255.255.255.252
 no shutdown

! EIGRP
router eigrp 1
 network 192.168.10.0
 network 192.168.100.0
 no auto-summary
🔧 Configuración de Router6
bash
Copiar
Editar
! Subinterfaz para VLAN 20
interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
 no shutdown

! Enlace hacia Router5
interface g0/1
 ip address 192.168.100.2 255.255.255.252
 no shutdown

! EIGRP
router eigrp 1
 network 192.168.20.0
 network 192.168.100.0
 no auto-summary
🔧 Configuración básica en los switches
En Switch8, Switch12 y Switch13 (lado izquierdo) y Switch14, Switch15, Switch16 (lado derecho):

bash
Copiar
Editar
! Ejemplo para Switch12 (repetir similar en otros switches de acceso)
interface range fa0/1 - 24
 switchport mode access
 switchport access vlan 10
 spanning-tree portfast
Y para el puerto troncal hacia el router:

bash
Copiar
Editar
interface fa0/x  ! (puerto hacia el router)
 switchport mode trunk
Reemplaza fa0/x con el puerto correcto hacia el router (por ejemplo, fa0/1).

💻 Configuración de los PCs
PC	IP	Gateway
PC2/PC3	192.168.10.X	192.168.10.1
PC4/PC5	192.168.20.X	192.168.20.1

✅ Comprobaciones
ping desde PC2 a PC4

show ip route en ambos routers para ver que aprendieron rutas con EIGRP

show ip protocols para confirmar EIGRP activo
