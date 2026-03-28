## Descripcion
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. `ssh -p 58704 ctf-player@mimas.picoctf.net` Use password: `6dd28e9b`
## Solucion
en este reto al conectarnos al servidor nos damos cuenta que no podemos usar letras ni algunos simbolos comunes de la consola de linux
entonces poniendo simbolos nos encontramos que por ejemplo poniendo /??? nos dice que bin es un directorio: 
```
SansAlpha$ /???
bash: /bin: Is a directory
```
usando esto encontramos que la bandera se encuentra en home/ctf-player/blargh/flag.txt ahora falta ver como abrirla, dentro de la carpeta /bin se encuentran los binarios como ls, cat, y chmod, el comando que en este caso nos podria servir es el de /bin/base64
que concuerda con la pista que nos dan del reto, entonces para acceder a ese directorio es con /???/????64 ya que al poner:
```
SansAlpha$ /???/??????
/bin/base32: extra operand '/bin/base64'
Try '/bin/base32 --help' for more information.
```
nos da error, por eso intentando poner el 64 al final nos deja:
```
SansAlpha$ /???/???[!_]64 /????/??????????/??????/????????
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30=
```
nos da un texto cifrado en base 64, lo decodificamos con el siguiente comando:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ echo "cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30=" | base64 -d
return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_145256ec}
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$
```
y obtenemos la bandera

## Notas
- 
## Referencias
- 