## Descripcion
We found this file. Recover the flag. [tunn3l_v1s10n](https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n)
## Solucion
descargamos el archivo del reto, y si lo revisamos con hexedit vemos que empieza BM algo asi entonces podemos deducir que es un archivo BMP
el archivo tiene unos bytes modificados y erroneos, tenemos que cambiar el data offset donde decia BA D0 por 36 00

despues devemos cambiar el tamaño de la cabecera DIB en vez de BA D0 ponemos 28 00

despues cambiamos 32 01 en la direccion 0x16 por 52 03 y listo abrimos la imagen y veremos la bandera: picoCTF{qu1t3_a_v13w_2020}
## Notas
- 
## Referencias
- 