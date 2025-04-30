# Tunel básico

En esta rama se propone una topología básica para manejar el uso de tuneles de ipv6 sobre ipv4

Hemos propuesto este tipo de tunel(ipv6 sobre ipv4) porque es el más usado actualmente
debido a que muchas redes aún siguen teniendo algunos elementos ipv4 y no todo en ipv6 
para asemejar este caso práctico con la realidad es una muy buena opción.

**A continuación se muestra una tabla de comparación entre los dos tipos de tuneles posibles**

| Criterio                     | IPv6 sobre IPv4 | IPv4 sobre IPv6 |
|-----------------------------|------------------|------------------|
| Compatibilidad actual       |  Alta            |  Baja (limitada) |
| Transición hacia IPv6       |  Ideal           |  Poco útil en la práctica actual |
| Uso futuro (IPv6-only)      |   Menor          |   Mayor         |
| Soporte en routers/switches |   Amplio         |  Limitado      |
