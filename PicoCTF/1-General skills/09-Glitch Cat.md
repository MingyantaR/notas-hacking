## Glitch Cat

## Descripcion
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 64778`
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc saturn.picoctf.net 64778
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python
Python 3.13.9 (main, Oct 15 2025, 14:56:22) [GCC 15.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(\0x35) + '}'
'picoCTF{gl17ch_m3_n07_bda68f75}'
>>>
```
picoCTF{gl17ch_m3_n07_bda68f75}
## Notas
- al usar el comando que nos da el reto nos da la mitad de la bandera= 'picoCTF{gl17ch_m3_n07_'
- la otra mitad de la bandera tiene lo que parecen comandos de python= chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
- chr() nos permite  convertir algun numero en su caracter equivalente
- si nos metemos a python y pegamos lo que nos dio el primero comando obtendremos la bandera entera =picoCTF{gl17ch_m3_n07_bda68f75}
## Referencias
- https://www.geeksforgeeks.org/python/chr-in-python/