## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key). Recover the flag.
## Solucion
al descargar el archivo del reto vemos que nos da un archivo que ya conocemos una captura de paquetes y una key

si abrimos el archivo en wireshark vamos a preferences rsa keys para añadir la llave que nos descargamos del reto, y despues en edit - find next escribimos picoCTF para encontrar la bandera y nos va a mandar directo en donde tenemos la bandera, damos click derecho copiar como ascii y obtenemos la bandera: Pico-Flag: picoCTF{nongshim.shrimp.crackers}

## Notas
- 
## Referencias
- 