## fixme2.py

## Descripcion
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python fixme2.py
  File "/home/min/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ sudo nano fixme2.py

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
```
## Notas
- Al ejecutar el programa del reto, nos da un error ya que se supone que deberia comparar en el if flag = "", pero al solo tener un = se le esta asignando a flag la cadena vacia
- El mismo error nos da la solucion en vez de tener = le agregamos otro == y asi compara y nos da la bandera = picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
## Referencias
- 