## Commitment Issues

## Descripcion
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in]
└─$ ls -la
total 16
drwxr-xr-x  3 min min 4096 Mar 11  2024 .
drwx------ 10 min min 4096 Feb 19 23:26 ..
drwxr-xr-x  8 min min 4096 Mar 11  2024 .git
-rw-r--r--  1 min min   11 Mar 11  2024 message.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in]
└─$ cd .git/

┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in/.git]
└─$ ls
branches  COMMIT_EDITMSG  config  description  HEAD  hooks  index  info  logs  objects  refs

┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in/.git]
└─$ git log
commit 42942c9c605b30100f5d859ef6e172027447c0db (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    remove sensitive info

commit b562f0b425907789d11d2fe2793e67592dc6be93
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    create flag

┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in]
└─$ git checkout b562f0b425907789d11d2fe2793e67592dc6be93
Note: switching to 'b562f0b425907789d11d2fe2793e67592dc6be93'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at b562f0b create flag

┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in]
└─$ ls
message.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~/drop-in]
└─$ cat message.txt
picoCTF{s@n1t1z3_c785c319}

```
## Notas
- extraemos el archivo del reto y entramos, si revisamos vemos que hay un .txt y un directorio oculto de git
- si entramos al directorio oculto y checamos el log del git vemos que hubo 2 cambios si revisamos el de create flag con un git checkout y su id entramos al repositorio antes del cambio
- ahora si revisamos con cat el message.txt vemos que esta la bandera sin eliminar 
## Referencias
- https://primer.picoctf.org/#_git_version_control