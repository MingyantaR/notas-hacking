## Descripcion
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
## Solucion
descargamos el archivo del reto, lo desencriptamos y obtenemos 2 txt con una lista larga de usuarios y contraseñas, si revisamos el usuario que dice el reto, que es el 378 en la lista observamos esto:
```
cultiris
cvpbPGS{P7e1S_54I35_71Z3}
```
tenemos lo que parece es la bandera, encriptada, si revisamos todas las banderas comienzan con picoCTF entonces cvpbPGS debe ser picoCTF, al parecer esta cifrado con ROT13 nos vamos a [cyberchef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=Y3ZwYlBHU3tQN2UxU181NEkzNV83MVozfQ&oeol=VT) y obtenemos la bandera:
```
picoCTF{C7r1F_54V35_71M3}
```

## Notas
- 
## Referencias
- 