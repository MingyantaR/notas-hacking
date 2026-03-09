## Descripcion
This is a really weird text file. Can you find the flag? Get the flag from [TXT](https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt).
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ file flag.txt
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ mv flag.txt flag.png

```
picoCTF{now_you_know_about_extensions}
## Notas
- El comando file nos permite ver que tipo de archivo es
- si revisamos el archivo .txt el comando nos dice que es un archivo PNG image data entonces renombramos el archivo de .txt a .png
- abrimos la imagen y veremos la bandera 
## Referencias
- 