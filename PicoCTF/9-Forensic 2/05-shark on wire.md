## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/edaf70675fae491d08043f5f626637436b05319785fa562e9274cdb4b09ec7ba/capture.pcap). Recover the flag.
## Solucion
analizando en wireshark el archivo, observando en los udp vemos que en el stream 32 y 60 hay unas marcas de begin y end, viendo que el puerto de destino es 22 podemos utilizar la herramienta tshark para agilizar las cosas:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ tshark -r capture.pcap.1 -Y "udp.dstport == 22" -T fields -e udp.srcport | python3 -c "import sys; print(''.join([ch
r(int(port)-5000) for port in sys.stdin if int(port) > 5000]))"
Warning: program compiled against libxml 215 using older 214
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
## Notas
- tshark es basicamente wireshark pero en linea de comandos 
## Referencias
- https://www.wireshark.org/docs/man-pages/tshark.html