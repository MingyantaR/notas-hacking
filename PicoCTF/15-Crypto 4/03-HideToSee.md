## Descripcion
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).
## Solucion
El reto nos da una imagen y en las pistas nos dice que la extraigamos, en la imagen vemos una tecnica de cifrado lammado atbash que consiste en tener el abecedario en orden normal y al reves en mayusculas y reemplazas con su equivalente por ejemplo a = Z y Z = a
entonces primero con la herramienta de steghide extraemos el texto cifrado en la imagen, nos dara un archivo de texto con el siguiente mensaje: krxlXGU{zgyzhs_xizxp_7142uwv9}
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/c4]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase:
wrote extracted data to "encrypted.txt".

┌──(min㉿WIN-U49VUBQG3G3)-[~/c4]
└─$ cat encrypted.txt
krxlXGU{zgyzhs_xizxp_7142uwv9}
```
ya tenemos lo que parece ser la bandera vamos a esta [pagina](https://www.dcode.fr/atbash-cipher) para descifrar el mensaje y obtener la bandera real: picoCTF{atbash_crack_7142fde9}
## Notas
- 
## Referencias
- 