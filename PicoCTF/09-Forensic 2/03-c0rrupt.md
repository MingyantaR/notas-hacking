## Descripcion
We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.
## Solucion
revisando el archivo del reto con file solo nos dice data entonces revisando con hexedit el archivo vemos esto:
```
00000000   89 65 4E 34  0D 0A B0 AA  00 00 00 0D  .eN4........
0000000C   43 22 44 52  00 00 06 6A  00 00 04 47
```
revisandolo detenidamente vemos que los primeros se parecen al header de un archivo PNG: 89 50 4E 47 0D 0A 1A 0A entonces cambiamos a esto del archivo:
```
00000000   89 50 4E 47  0D 0A 10 0A  00 00 00 0D  .PNG........
0000000C   43 22 44 52  00 00 06 6A  00 00 04 47  C"DR...j...G
```
viendolo bien, un archivo png usualmente empieza con un chunk IHDR tambien
vemos que dice C"DR entonces si cambiamos esto:
```
00000000   89 50 4E 47  0D 0A 10 0A  00 00 00 0D  .PNG........
0000000C   49 48 44 52  00 00 06 6A  00 00 04 47  IHDR...j...G
```
ahora checandolo otra vez con pngcheck
nos repite esto muchas veces:
```
mystery  private (invalid?) IDAT row-filter type (255) (warning)
mystery  private (invalid?) IDAT row-filter type (255) (warning)
mystery  private (invalid?) IDAT row-filter type (255) (warning)
mystery  private (invalid?) IDAT row-filter type (255) (warning)
```
y al final dice esto:
```
mystery  CRC error in chunk IDAT (computed ab33bf2a, expected b6cf0000)
ERROR: mystery
```
esto quiere decir que solo falta que el sello de seguridad CRC coincida con los datos que cambiamos anteriormente, vamos en hexedit al final del archivo y cambiamos en donde dice B6 CF 00 00 por los valores en computed AB 33 BF 2A
entonces abrimos la imagen y obtenemos la bandera: picoCTF{c0rrupt10n_1847995}

## Notas
- 
## Referencias
- 