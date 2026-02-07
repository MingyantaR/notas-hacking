## Plumbing
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?
Connect to fickle-tempest.picoctf.net 58684.
## Descripcion
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?
Connect to fickle-tempest.picoctf.net 58684.
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc fickle-tempest.picoctf.net 58684 | grep picoCTF
picoCTF{digital_plumb3r_1eBfC512}
```
## Notas
- al usar | en linux nos permite procesar los datos a traves de una serie de comandos
-  usamos el nc para acceder al reto y lo que nos devuelve usamos grep para filtrar y encontrar la bandera picoCTF
## Referencias
- https://www.geeksforgeeks.org/linux-unix/piping-in-unix-or-linux/