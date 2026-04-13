## Descripcion
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).
## Solucion
descargamos el archivo del reto y lo revisamos, al pareces esta cifrado en base64
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag.1
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==
```
entonces decodificamos el mensaje:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag.1
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag.1 | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag.1 | base64 -d | tr -d "'b"
d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ==

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag.1 | base64 -d | tr -d "'b" | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}
```
ahora vamos al cyberchef elegimos ROT13 y ponemos en amount 19
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,19)&input=d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ
y la bandera nos queda asi: picoCTF{caesar_d3cr9pt3d_a47c6d69}

## Notas
- 
## Referencias
- 