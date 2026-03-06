## Roboto Sans

## Descripcion
The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:56646/) out.
## Solucion
al entrar a la pagina del reto probe algunas cosas de los menus y nada funcionaba entonces viendo el nombre del reto recorde que existia el robots.txt, revisandolo me encontre con estos mensajes:
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

al parecer hay un texto en base64 si lo decodificamos podemos observar esto:

```
└─$ echo "ZmxhZzEudHh0anMvbXlmaW" | base64 -d
flag1.txtjs/myfibase64: invalid input

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ echo "anMvbXlmaWxlLnR4dA==" | base64 -d
js/myfile.txt
```
flag1.txt y js/myfile.txt entonces revisamos por ejemplo el de myfile:
http://saturn.picoctf.net:56646/js/myfile.txt
y nos encontramos con la bandera:
picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}
## Notas
- 
## Referencias
- 