## Strings it

## Descripcion
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/53c039e64942b1c4334781c4987ba7e2ba54f0b2bf39f52c65f3a65dfcbf4194/strings) without running it?
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ strings strings | grep pico
picoCTF{5tRIng5_1T_A1b9ECAa}
```
picoCTF{5tRIng5_1T_A1b9ECAa}
## Notas
- El comando strings nos ayuda a extraer secuencias de caracteres imprimibles de archivos binarios
## Referencias
- https://www.ibm.com/docs/en/aix/7.2.0?topic=s-strings-command