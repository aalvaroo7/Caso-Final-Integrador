# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git


# Servicios que ofrece el Ayto. de Coslada a los que hay que implementar un sistema de conexión

![image](https://github.com/user-attachments/assets/cb0bc9ed-2afb-47b4-ac5c-1d4304016382)

Hemos planteado ofrecer una red para cada servicio dividiendo así la red en la red principal (la ubicada En el Ayto. de Coslada) y otras subredes en las cuales se alojarán los distintos servicios, además ofreceremos una propuesta para situar estas redes de forma que no haya que emplear un mayor gasto en 

##  Para ello hemos dividido los servicios según la categoría funcional
| **Categoría Funcional**                   | **Servicios del Ayuntamiento de Coslada**                                                                 |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 🏛️ **Servicios Gubernamentales**         | - Archivo <br> - Contratación <br> - Economía, Empleo, Comercio, Turismo y Transición Energética <br> - Educación <br> - Hacienda <br> - Participación Ciudadana, Cooperación y Atención a la Ciudadanía <br> - Recursos Humanos <br> - Secretaría General <br> - Urbanismo <br> - Vivienda |
| 🚨 **Seguridad Pública y Emergencias**   | - Seguridad y Emergencias <br> - Salud, Consumo y Bienestar Animal <br> - Igualdad y Diversidad <br> - Mayores <br> - Infancia |
| 🚦 **Transporte y Monitoreo Ambiental**  | - Parques, Jardines y Limpieza Viaria <br> - Transición Ecológica, Movilidad y Transporte <br> - Vías y Obras <br> - Servicios Generales |
| 📺 **Servicios Multimedia para el Ciudadano** | - Cultura <br> - Deportes <br> - Juventud <br> - Servicios Sociales <br> - Informática |

![image](https://github.com/user-attachments/assets/f5626333-aaa4-45ff-80be-8acc8db0bb99)

##  Para cumplir con todo esto hemos planteado dividir la red en varias sedes con varias subredes, en total se ha planteado 4 sedes

![Sedes - visual selection (1)](https://github.com/user-attachments/assets/7ebe393b-baaf-4c08-b2ad-b4a7d55ae793)

| **Sede**        | **Función Principal**                                              | **Servicios albergados**                                                                                                                                                          |
|------------------|--------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 🏛️ **Sede Central** | Núcleo de red, enrutamiento, VPN/IPsec, servicios administrativos clave | - Secretaría General  <br> - Hacienda  <br> - Urbanismo  <br> - Recursos Humanos <br> - Participación Ciudadana <br> - **VPN / IPsec / Routing entre sedes**                      |
| 🚨 **Sede de Seguridad** | Seguridad Pública y Emergencias                              | - Seguridad y Emergencias <br> - Salud, Consumo y Bienestar Animal <br> - Igualdad y Diversidad <br> - Mayores <br> - Infancia                                                    |
| 🚦 **Sede de Infraestructura** | Transporte y Monitoreo Ambiental                         | - Parques, Jardines y Limpieza Viaria <br> - Transición Ecológica, Movilidad y Transporte <br> - Vías y Obras <br> - Servicios Generales                                          |
| 📺 **Sede Ciudadana y Multimedia** | Servicios para el ciudadano, cultura, digitalización       | - Cultura <br> - Deportes <br> - Juventud <br> - Servicios Sociales <br> - Informática                                                                                             |

Notas técnicas
Cada sede tendrá subredes individuales por servicio, como planeaste.

La Sede Central dispondrá de:

Firewall/VPN Gateway para acceso remoto seguro.

Enrutador principal con políticas de seguridad (ACL, NAT si aplica).

Conexiones troncales con cada sede usando GRE/IPsec sobre IPv4.

Las demás sedes funcionarán como sucursales LAN conectadas al core central.
