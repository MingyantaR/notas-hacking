## Descripcion
Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png).
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$ exiftool pico_img.png
ExifTool Version Number         : 13.36
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2025:11:21 13:11:04-06:00
File Access Date/Time           : 2026:03:09 12:28:45-06:00
File Inode Change Date/Time     : 2026:03:09 12:28:45-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_74af23ab}
Image Size                      : 600x600
Megapixels                      : 0.360

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic]
└─$
```
## Notas
- Para este reto usamos la herramienta exiftool para poder revisar los metadatos de la imagen del reto
- la bandera esta en donde dice artist: picoCTF{s0_m3ta_74af23ab}
## Referencias
- 