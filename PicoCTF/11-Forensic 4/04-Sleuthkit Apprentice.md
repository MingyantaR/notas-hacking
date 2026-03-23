## Descripcion
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)
## Solucion
descargamos y descomprimimos el archivo del reto, despues con mmls vemos que particiones existen en el archivo y listamos los archivos de la primer particion:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ fls -o 2048 disk.flag.img
d/d 11: lost+found
r/r 12: ldlinux.sys
r/r 13: ldlinux.c32
r/r 15: config-virt
r/r 16: vmlinuz-virt
r/r 17: initramfs-virt
l/l 18: boot
r/r 20: libutil.c32
r/r 19: extlinux.conf
r/r 21: libcom32.c32
r/r 22: mboot.c32
r/r 23: menu.c32
r/r 14: System.map-virt
r/r 24: vesamenu.c32
V/V 25585:      $OrphanFiles
```
aqui no vemos nada que nos de una pista de donde esta la bandera entonces vemos la otra particion, nos dara una lista muy grande de archivos, pero lo que nos interesa es lo que esta al final, vemos que hay un archivo flag.txt que fue movido y renombrado a flag.uni.txt, lo revisamos con icat y la direccion del archivo y obtenemos la bandera

```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ fls -o 2048 disk.flag.img
d/d 11: lost+found
r/r 12: ldlinux.sys
r/r 13: ldlinux.c32
```
...
...
...
```
+ r/r 2363:     .ash_history
+ d/d 3981:     my_folder
++ r/r * 2082(realloc): flag.txt
++ r/r 2371:    flag.uni.txt
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/forensic4]
└─$ icat  -o 360448 -r disk.flag.img 2371
picoCTF{by73_5urf3r_2f22df38}
```
## Notas
- 
## Referencias
- 