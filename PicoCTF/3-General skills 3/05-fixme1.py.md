## fixme1.py

## Descripcion
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python fixme1.py
  File "/home/min/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ sudo nano fixme1.py

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}

```
## Notas
- Descargamos el programa que nos da el reto y lo ejecutamos, nos da un error
- El error ocurre ya que python interpreta los espacios y tabs diferente, en este caso el print tiene un espacio antes de el print y esto es lo que causa el error
- Borramos ese espacio, lo ejecutamos de nuevo y nos da la bandera= picoCTF{1nd3nt1ty_cr1515_6a476c8f}
## Referencias
- https://discuss.python.org/t/unexpected-indentation-error-or-is-it-likely-the-interpreter-is-wrong/21385/5