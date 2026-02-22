## Reto

## Descripcion
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/159/challenge.zip)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame]
└─$ ls
challenge.zip  drop-in

┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame]
└─$ cd drop-in/

┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame/drop-in]
└─$ ls
message.py

┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame/drop-in]
└─$ cat message.py
print("Hello, World!"

┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame/drop-in]
└─$ python message.py
  File "/home/min/T106_Blamegame/drop-in/message.py", line 1
    print("Hello, World!"
         ^
SyntaxError: '(' was never closed

┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame/drop-in/.git]
└─$ git log
commit 929e3918bed4c8f3432c1f7c7ddfe5b378e177e1 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

commit 5611f02bbfed52af8c78eb92ec58a323bebf96da
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:17 2024 +0000

    important business work

...
...
...

commit 80f6ecce9660dbab8e7c6e703a5dddd8fb7291ab
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    important business work

commit 23e9d4ce78b3cea725992a0ce6f5eea0bf0bcdd4
Author: picoCTF{@sk_th3_1nt3rn_81e716ff} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    optimize file size of prod code

commit 3ce5c692e2f9682a866c59ac1aeae38d35d19771
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:15 2024 +0000

    create top secret project

[1]+  Stopped                    git log

┌──(min㉿WIN-U49VUBQG3G3)-[~/T106_Blamegame/drop-in/.git]
└─$

```
## Notas
- el reto menciona que alguien hizo un cambio en el repositorio y que no funciona el programa por su culpa, si revisamos el historial con un git log, va a mostrar muchos cambios pero si damos hasta el ultimo, vemos que el autor es diferente y es donde se encuentra nuestra bandera : picoCTF{@sk_th3_1nt3rn_81e716ff}
## Referencias
- 