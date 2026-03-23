## Descripcion
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ gzip -d disk.flag.img.gz
gzip: disk.flag.img already exists; do you wish to overwrite (y or n)? y

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ icat -i raw -o 411648 disk.flag.img 1875
touch flag.txt
nano flag.txt
apk get nano
apk --help
apk add nano
nano flag.txt
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ icat -o 411648  disk.flag.img 1782
Salted__�ށ��e��B�J�c�$QE&$��4jM�KGeE�1�^Ȥ7� ���؎$�'%
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ icat -o 411648  disk.flag.img 1782 > flag.txt.enc

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
404749DBD9720000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ cat flag.txt
picoCTF{h4un71ng_p457_5113beab}
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$
```
## Notas
decargamos y descomprimimos el archivo del reto, es una imagen de disco, vemos las particiones que tiene la imagen y despues vemos los archivos en la particion de linux donde estan los datos
despues revisamos el archivo de historial de comandos para ver como fue encriptada la bandera, revisamos el archivo que contiene la bandera con icat y despues la guardamos en un archivo local, desencriptamos la bandera usando las operaciones inversas que se usaron para encriptarla y revisamos el archivo con un cat para obtener la bandera: picoCTF{h4un71ng_p457_5113beab}
## Referencias
- 