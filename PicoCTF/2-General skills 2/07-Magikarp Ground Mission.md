## Magikarp Ground Mission

## Descripcion
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `8c606eb1` on the host `wily-courier.picoctf.net` and port `62877`.
## Solucion 
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ ssh ctf-player@wily-courier.picoctf.net -p62877
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@wily-courier.picoctf.net's password:
Welcome to Ubuntu 18.04.6 LTS (GNU/Linux 6.14.0-1012-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Thu Feb 12 03:43:56 2026 from 127.0.0.1
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ pwd
/home/ctf-player/drop-in
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ pwd
/
ctf-player@pico-chall$ ls
2of3.flag.txt  boot       dev  home                      lib    media  opt   root  sbin  sys  usr
bin            challenge  etc  instructions-to-3of3.txt  lib64  mnt    proc  run   srv   tmp  var
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_//4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd home/
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ cd ctf-player/
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt
0b24fc4f}ctf-player@pico-chall$
ctf-player@pico-chall$
```
## Notas
- mediante ssh accediendo con las credenciales que nos da el reto si ejecutamos ls podemos ver los archivos que hay en ese directorio
- tenemos 2 txt 1 que forma parte de la bandera y otro que nos dice instrucciones para llegar a la otra parte de la bandera
- con cat los revisamos y obtenemos 1of3.flag.txt = picoCTF{xxsh_ y el 2do dice que vallamos a la raiz de las cosas, esto se refiere que vayamos al directorio raiz
- si usamos pwd podemos ver en que directorio nos encontramos = /home/ctf-player/drop-in
- si salimos de las 3 carpetas en las que estamos llegaremos al directorio raiz donde se encuentran otros 2 archivos (2of3.flag.txt,  instructions-to-3of3.txt)
- los revisamos y obtenemos mas de la bandera =picoCTF{xxsh_0ut_0f_//4t3r_ y otra instruccion que nos dice que vallamos al directorio home
- ya dentro de home encontramos un ultimo txt donde obtendremos la parte final de la bandera picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}
## Referencias