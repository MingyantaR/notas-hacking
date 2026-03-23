## Descripcion
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory. [Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz) Access checker program: `nc saturn.picoctf.net 53237`
## Solucion
descargamos el archivo del reto, lo descomprimimos y usamos mmls para ver las particiones del disco, con esta informacion respondemos la pregunta del servidor del reto:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ nc saturn.picoctf.net 53237
What is the size of the Linux partition in the given disk image?
Length in sectors: 2047
2047
That is not correct. Feel free to try again.

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ nc saturn.picoctf.net 53237
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$
```
y obtenemos la bandera: picoCTF{mm15_f7w!}
## Notas
- 
## Referencias
- 