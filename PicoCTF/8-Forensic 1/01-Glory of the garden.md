## Descripcion
This file contains more than it seems. Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/26ad1e959e2e6f15113d4dc2b43649625499d960e546d1b874357c6fcb8c5229/garden.jpg).
## Solucion

```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ strings garden.jpg | grep picoCTF
Here is a flag: picoCTF{more_than_m33ts_the_3y333f84d7c}

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$
```
## Notas
- Descargamos el archivo del reto y usamos el comando para obtener la bandera
- El comando strings nos permite extraer secuencias de caracteres de archivos binarios
## Referencias
- https://linux.die.net/man/1/strings