DISKO 4

Description
Description
Can you find the flag in this disk image? This time I deleted the file! 
Let see you get it now! 
Download the disk image here.

Solución 

picoCTF{d3l_d0n7_h1d3_w3ll_fe34c2cb}

Notas adicionales

Recuperación: se utilizo tsk_recover para escanear la imagen de disco (.dd). Esta herramienta buscó inodos 
(índices de archivos) que el sistema marcó como "borrados" pero cuyos datos seguían físicamente en los 
sectores del disco.

Identificación: De los 65 archivos rescatados, se descarto una anomalía en /var/log: el archivo dont-delete.gz. 
Su nombre era una pista directa y su extensión indicaba que el contenido estaba comprimido (y por tanto, invisible para un grep normal).

Extracción: Al usar gunzip, se descomprimieron los datos, transformando el código binario de vuelta a texto
plano, revelando la flag.

```
fergll@FerGLl:/mnt/c/Users/ferch/documents$ cp recuperado/log/dont-delete.gz .
fergll@FerGLl:/mnt/c/Users/ferch/documents$ gunzip dont-delete.gz
fergll@FerGLl:/mnt/c/Users/ferch/documents$ cat dont-delete
Here is your flag
picoCTF{d3l_d0n7_h1d3_w3ll_fe34c2cb}

```

Referencias
