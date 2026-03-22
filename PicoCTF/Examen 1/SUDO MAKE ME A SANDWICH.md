## Descripcion
Can you read the flag? I think you can! `ssh -p 63656 ctf-player@green-hill.picoctf.net` using password `deebe023`
## Solucion
```
ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
cat: flag.txt: Permission denied
ctf-player@challenge:~$ sudo cat flag.txt
[sudo] password for ctf-player:
Sorry, user ctf-player is not allowed to execute '/usr/bin/cat flag.txt' as root on challenge.
ctf-player@challenge:~$ sudo -l
Matching Defaults entries for ctf-player on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User ctf-player may run the following commands on challenge:
    (ALL) NOPASSWD: /bin/emacs
ctf-player@challenge:~$ sudo emacs flag.txt

```
## Notas
- Al entrar con ssh al reto, use ls para ver que archivos habia en el directorio estaba flag.txt
- al intentar ver que tenia con cat me decia que no tenia permisos y no podia usar sudo tampoco para ver que tenia el .txt
- con sudo -l nos permite ver que comandos tenemos permitidos ejecutar con sudo, vemos que dice /bin/emacs buscando un poco vemos que emacs es un editor de texto entonces con esto podemos abrir el archivo flag.txt
- al abrir flag.txt obtenemos la bandera: picoCTF{ju57_5ud0_17_cce7a3f7}
## Referencias
- https://www.gnu.org/software/emacs/