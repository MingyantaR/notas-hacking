## special

## Descripcion
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM) Start your instance to see connection details. `ssh -p 60335 ctf-player@saturn.picoctf.net` The password is `af86add3`
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ ssh -p 60335 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:60335 ([13.59.203.175]:60335)' can't be established.
ED25519 key fingerprint is: SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:14: [hashed name]
    ~/.ssh/known_hosts:16: [hashed name]
    ~/.ssh/known_hosts:17: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:60335' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.8.0-1044-aws x86_64)

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

Special$ ((ls))
((ls))
blargh
Special$((cat)) < blargh
((cat)) < large
sh: 1: cannot open large: No such file
Special$ ((ls)) < -la
((cls)) < la
sh: 1: cannot open la: No such file
Special$ ((cat)) < blargh/flag.txt
((cat)) < blargh/flag.txt
picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}Special$

```
## Notas
- al poner un comando entre parentesis nos permite ejecutarlo en un subshell de linux
- al parecer el script tiene una forma rara de modificar los comandos por lo que ejecutandolos en el subshell nos permite correrlo de manera normal, aun asi hay limitaciones
- al ejecutar el comando ls de este modo podemos ver que hay algo llamado blargh no sabemos si un directorio o archivo 
- al final no supe muy bien como pero con < es como que le esta pasando los argumentos del comando al comando de esa forma rara por el script asi que asi obtenemos la bandera:picoCTF{5p311ch3ck_15_7h3_w0r57_6a2763f6}Special$
## Referencias
- https://unix.stackexchange.com/questions/138463/do-parentheses-really-put-the-command-in-a-subshell
De aqui saque la mayoria del reto:
- https://github.com/snwau/picoCTF-2023-Writeup/blob/main/General%20Skills/Special/Special.md