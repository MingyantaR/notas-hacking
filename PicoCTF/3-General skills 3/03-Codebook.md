## Codebook

## Descripcion
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ wget https://artifacts.picoctf.net/c/3/code.py
--2026-02-13 16:26:01--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.105, 13.225.222.125, 13.225.222.28, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.105|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: ‘code.py’

code.py                       100%[=================================================>]   1.25K  --.-KB/s    in 0s

2026-02-13 16:26:02 (4.31 MB/s) - ‘code.py’ saved [1278/1278]


┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2026-02-13 16:28:32--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.120, 13.225.222.28, 13.225.222.125, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: ‘codebook.txt’

codebook.txt                  100%[=================================================>]      27  --.-KB/s    in 0s

2026-02-13 16:28:33 (626 KB/s) - ‘codebook.txt’ saved [27/27]


┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
```

## Notas
- Este reto descargamos los 2 archivos del reto y ejecutamos el programa de python, si el .txt esta en el mismo directorio nos dara la bandera =picoCTF{c0d3b00k_455157_197a982c}
- Parece que el codigo utiliza el metodo de cifrado XOR, una cadena de texto es cifrada aplicando el  operador de bit XOR sobre cada uno de los caracteres utilizando una clave, para descifrar la salida, solo hay que volver a aplicar el operador XOR con la misma clave
## Referencias
- https://es.wikipedia.org/wiki/Cifrado_XOR