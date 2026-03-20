## Descripcion
I've hidden a flag in this file. Can you find it? [Forensics_is_fun.pptm](https://challenge-files.picoctf.net/c_wily_courier/d78815176c19ddc85a1388233268d2f4c459fcbbaab197b4a29ebafc88294c54/Forensics_is_fun.pptm)
## Solucion
Descargamos el archivo del reto, primero verificamos que tipo de archivo es con file: 
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ file Forensics_is_fun.pptm
Forensics_is_fun.pptm: Microsoft PowerPoint 2007+
```
podemos desencriptar el archivo asi que lo hacemos con unzip y nos damos cuenta que hay un archivo llamado hidden
```
inflating: ppt/slideMasters/hidden
```
nos vamos al directorio donde se encuentra ese archivo y lo revisamos con cat, vemos que contiene algo codificado en base64 con espacios entonces lo decodificamos para obtener la bandera:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/ppt/slideMasters]
└─$ ls -la
total 32
drwxr-xr-x 3 min min  4096 Mar 19 19:02 .
drwxr-xr-x 7 min min  4096 Mar 19 19:02 ..
-rw-r--r-- 1 min min    99 Oct 23  2020 hidden
drwxr-xr-x 2 min min  4096 Mar 19 19:02 _rels
-rw-r--r-- 1 min min 13875 Jan  1  1980 slideMaster1.xml

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/ppt/slideMasters]
└─$ cat hidden
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 .d
base64: .d: No such file or directory

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/ppt/slideMasters]
└─$
```
## Notas
- 
## Referencias
- 