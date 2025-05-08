# Caso-Final-Integrador
https://github.com/aalvaroo7/Caso-Final-Integrador.git
#Demostración del servicio ftp:

Para ello emplearemos en el apartado de comand prompt en el desktop del pc los comandos:

put y get con el nombre del archivo, entonces si el servidor soporta estos comandos y efectivamente se encarga de obtener archivos (get) y de subir archivos (put) significará que se ha cumplido con la funcionalidad del servicio de ftp

a continuación se adjuntan captuas con la demostración del correcto funcionamiento de este servicio:

En esta imagen se ve como se ha añadido un archivo llamado Texto.txt al servidor

![image](https://github.com/user-attachments/assets/09864639-dd20-4150-b01a-73795a6c9000)

En esta imagen se visualiza la correcta descarga del archivo Texto.txt desde otro pc desde el servidor hacia este 

![image](https://github.com/user-attachments/assets/5dbdd836-0c88-4dac-9b13-64b7bad1e010)


# Demostración servicio tfpt

para hacer uso de este servicio introduciremos los siguientes comandos en un router para copiar la configuración de este y transferirla al server

```
Copy running-config tftp:
Address or name of remote host []? 192.168.1.2
Destination filename [netizzan-confg]? 
Writing running-config....!!
[OK - 718 bytes]
718 bytes copied in 3.252 secs (220 bytes/sec)
```

En esta imagen se ve como el server ha sido capaz de obtener la configuración desde un router 
![image](https://github.com/user-attachments/assets/ca253d38-ea88-4290-9f27-56ea3ac18ac8)
