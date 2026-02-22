## Time Machine

## Descripcion
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/67/challenge.zip)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine]
└─$ ls
challenge.zip  drop-in

┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine]
└─$ cd drop-in/

┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine/drop-in]
└─$ ls
message.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine/drop-in]
└─$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...
┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 min min 4096 Mar  9  2024 .
drwxr-xr-x 3 min min 4096 Feb 21 18:02 ..
drwxr-xr-x 8 min min 4096 Mar  9  2024 .git
-rw-r--r-- 1 min min   87 Mar  9  2024 message.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine/drop-in]
└─$ cd .git/

┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine/drop-in/.git]
└─$ git l
lfs   log
┌──(min㉿WIN-U49VUBQG3G3)-[~/T105_TimeMacine/drop-in/.git]
└─$ git log
commit b92bdd8ec87a21ba45e77bd9bed3e4893faafd0f (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:29 2024 +0000

    picoCTF{t1m3m@ch1n3_5cde9075}

```
## Notas
- el reto nos da un archivo zip con un archivo de texto y una carpeta oculta de un repositorio de github
- si checamos el historial del repositorio con git log, vemos que en ese cambio que hubo el mensaje fue la bandera : picoCTF{t1m3m@ch1n3_5cde9075}
## Referencias
- 