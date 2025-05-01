# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git


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
| 🏛️ **Sede Central**              | - Comunicación interorganismos<br>- DNS, NTP, AAA<br>- Administración interna<br>- Control de políticas de red          | - Core de ruteo (OSPF)<br>- Firewall perimetral<br>- VPN Gateway/IPSec<br>- ACLs y NAT              |
| 🚨 **Sede de Seguridad**         | - Cámaras de videovigilancia<br>- Comunicaciones de emergencia<br>- Salud y Protección Civil                            | - QoS para voz/video<br>- Alta disponibilidad<br>- Red inalámbrica segura<br>- Segmentación IoT     |
| 🚦 **Sede de Infraestructura**   | - Semáforos inteligentes<br>- Sensores ambientales (aire, humedad, ruido)<br>- Movilidad urbana                          | - VLANs por tipo de sensor<br>- Protocolo SNMP/MQTT<br>- Enlaces redundantes<br>- Túneles GRE/IPsec |
| 📺 **Sede Ciudadana y Multimedia** | - Streaming de eventos<br>- Kioskos digitales<br>- WiFi ciudadano<br>- Acceso a portales e información pública          | - DMZ protegida<br>- DNSSEC, HTTPS<br>- Captive Portal<br>- Segmentación red pública/interna        |

Notas técnicas
Cada sede tendrá subredes individuales por servicio

La Sede Central dispondrá de:

Firewall/VPN Gateway para acceso remoto seguro.

Enrutador principal con políticas de seguridad (ACL, NAT si aplica).

Conexiones troncales con cada sede usando GRE/IPsec sobre IPv4.

Las demás sedes funcionarán como sucursales LAN conectadas al core central.
