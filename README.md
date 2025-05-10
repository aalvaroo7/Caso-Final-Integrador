## Como se aplicó ipv6 al proyecto

Para cubrir la necesidad de ipv6 para los servicios de multimedia se ha empleado un módulo de ipv6 y se ha empleado el dual stack, que consiste en habilitar ambos tipo de ip (ipv4 e ipv6) para que se emplee la ipv4 para conectarse con el resto de dispositivos de la red (puesto a que la mayoría tienen ipv4) y para conectarse entre ellos se emplea la ipv6

## Seguridad de la red

Para añadir cierta seguridad se ha planteado la siguiente situación, Los ciudadanos tendrán su propio módulo con el que podrán acceder al servicio de ftp y ftfp el cual está situado en la vlan 40 pero no tendrán acceso al resto de pcs que se encargan de obsvservar las cámaras de seguridad y gestionar los dispositivos Iot y para cumplir con todo esto emplearemos acls.

Para ello definiremos que las **Access Control Lists (ACLs)** son reglas aplicadas en routers y switches que permiten o deniegan el paso de tráfico. Se clasifican principalmente en **ACLs estándar** y **ACLs extendidas**, dependiendo del nivel de detalle con el que filtran el tráfico.

Más concretamente usarmos las ACL extendidas:

ACL Extendida

Las **ACL extendidas** permiten un filtrado mucho más detallado. Pueden evaluar **IP de origen y destino, protocolos, y puertos**, lo que las hace ideales para controlar servicios específicos como HTTP, FTP, SSH, etc.

###  Características de ACL Extendida

| Característica              | Descripción                                                           |
|----------------------------|-----------------------------------------------------------------------|
| Nivel de filtrado          | Dirección IP de **origen y destino**, **protocolo** y **puertos**     |
| Protocolos soportados      | IP, TCP, UDP, ICMP, etc.                                              |
| Rango numérico             | `100–199` y `2000–2699`                                               |
| Complejidad                | Alta, más flexible y potente                                          |
| Ubicación recomendada      | **Cerca del origen**, para descartar tráfico innecesario desde el inicio |
| Uso común                  | Permitir o denegar tráfico según aplicaciones o servicios específicos  |****
