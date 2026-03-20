## Descripcion
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/f1f4181c217358672b720e801df28731166311181fd73b364baa4479f8500044/dolls.jpg)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
unz0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg
651591        0x9F147         End of Zip archive, footer length: 22

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ unzip dolls.jpg
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ ls
base_images     final_flag.png  mystery            webnet1
buildings.png   flag.png        mystery_fixed.png  whitepages.txt
capture.pcap    garden.jpg      pico_img.png
capture.pcap.1  like1000        the_real_flag.png
dolls.jpg       message.wav     webnet0

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ cd base_images/

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/base_images]
└─$ ls
2_c.jpg
...
...
...
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/base_images/base_images/base_images]
└─$ unzip 4_c.jpg
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
 extracting: flag.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/base_images/base_images/base_images]
└─$ ls
4_c.jpg  flag.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/base_images/base_images/base_images]
└─$ cat flag.txt
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}

```
## Notas
- al revisar el archivo con el comando binwalk podemos ver que tiene un archivo .zip adentro
- procedemos a desencriptar el archivo con unzip hasta encontrar la bandera revisamos el .txt y obtenemos la bandera: picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}

## Referencias
- 