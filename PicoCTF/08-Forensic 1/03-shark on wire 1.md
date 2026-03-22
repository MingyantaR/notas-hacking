## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.
## Solucion
El reto nos da un archivo capture.pcap que es un archivo que nos sirve para capturar el trafico de paquetes que ocurre en la red

abrimos wireshark buscamos cualquier paquete que tenga transmision UDP y damos a la opcion follow y la opcion que sale ahi si revisamos el stream 6 encontraremos la bandera:
picoCTF{StaT31355_636f6e6e}

## Notas
- 
## Referencias
- https://www.endace.com/learn/what-is-a-pcap-file