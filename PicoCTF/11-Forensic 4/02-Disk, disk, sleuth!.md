## Descripcion
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image. [dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/ae15f331b193f3e33b88ebbd7a054b6d48af0e2d8b79c53805b3eeab7cf2c9e5/dds1-alpine.flag.img.gz)
## Solucion
El reto nos da un archivo de imagen de disco, usamos sleuthkit que es una herramienta que nos permite analizar imagenes de disco en busca de, en este caso, la bandera del reto:
primero descomprimimos el archivo y para asegurarnos revisamos que tipo de archivo es el del reto
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ file dds1-alpine.flag.img
dds1-alpine.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0x10,81,1), startsector 2048, 260096 sectors
```
vemos que en efeto es una imagen de disco de DOS, ahora con sleuthkit buscamos cadenas dentro de la imagen y las filtramos con el siguiente comando:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
```
y asi encontramos la bandera:
picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}
## Notas
- 
## Referencias
- 