## Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key). Recover the flag.
## Solucion
Descargamos los archivos del reto y vemos que son igual que el anterior una captura de paquetes que podemos abirr en wireshark y un archivo key
podemos decodificar el paquete usando la llave rsa con ssldump:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/webnet1]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pi -A 10
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
    65 6e 74 2d 4c 65 6e 67 74 68 3a 20 38 34 37 0d    ent-Length: 847.
    0a 4b 65 65 70 2d 41 6c 69 76 65 3a 20 74 69 6d    .Keep-Alive: tim
    65 6f 75 74 3d 35 2c 20 6d 61 78 3d 31 30 30 0d    eout=5, max=100.
    0a 43 6f 6e 6e 65 63 74 69 6f 6e 3a 20 4b 65 65    .Connection: Kee
    70 2d 41 6c 69 76 65 0d 0a 43 6f 6e 74 65 6e 74    p-Alive..Content
    2d 54 79 70 65 3a 20 74 65 78 74 2f 68 74 6d 6c    -Type: text/html
    0d 0a 0d 0a 1f 8b 08 00 00 00 00 00 00 03 a5 55    ...............U
    5d 77 a2 3a 14 7d 6e 7f 45 ca 6b 0b 91 91 aa bd    ]w.:.}n.E.k.....
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
    6e 74 2d 4c 65 6e 67 74 68 3a 20 31 30 30 0d 0a    nt-Length: 100..
    4b 65 65 70 2d 41 6c 69 76 65 3a 20 74 69 6d 65    Keep-Alive: time
    6f 75 74 3d 35 2c 20 6d 61 78 3d 31 30 30 0d 0a    out=5, max=100..
    43 6f 6e 6e 65 63 74 69 6f 6e 3a 20 4b 65 65 70    Connection: Keep
    2d 41 6c 69 76 65 0d 0a 43 6f 6e 74 65 6e 74 2d    -Alive..Content-
    54 79 70 65 3a 20 74 65 78 74 2f 63 73 73 0d 0a    Type: text/css..
    0d 0a 1f 8b 08 00 00 00 00 00 00 03 4b ca 4f a9    ............K.O.
    54 a8 e6 52 50 28 48 4c 49 c9 cc 4b d7 2d c9 2f    T..RP(HLI..K.-./
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
    Content-Type: image/jpeg

    ---------------------------------------------------------------
1 15 0.5802 (0.0294)  S>C  application_data
    ---------------------------------------------------------------
    ff d8 ff e0 00 10 4a 46 49 46 00 01 01 00 00 01    ......JFIF......
    00 01 00 00 ff e1 00 82 45 78 69 66 00 00 4d 4d    ........Exif..MM
    00 2a 00 00 00 08 00 05 01 1a 00 05 00 00 00 01    .*..............
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
    50 52 4f 46 49 4c 45 00 01 01 00 00 02 0c 6c 63    PROFILE.......lc
    6d 73 02 10 00 00 6d 6e 74 72 52 47 42 20 58 59    ms....mntrRGB XY
    5a 20 07 dc 00 01 00 19 00 03 00 29 00 39 61 63    Z .........).9ac
    73 70 41 50 50 4c 00 00 00 00 00 00 00 00 00 00    spAPPL..........
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00    ................
    f6 d6 00 01 00 00 00 00 d3 2d 6c 63 6d 73 00 00    .........-lcms..
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00    ................
    00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00    ................
--
    32 3d 94 6d a9 70 69 08 cd 3b 8b 95 91 15 1e b4    2=.m.pi..;......
    da 90 ad 44 41 ab bb b1 36 42 e2 9e 0d 34 52 8a    ...DA...6B...4R.
    0a b5 c5 26 98 7a 52 d1 8c d2 15 ac 30 1c 8c e2    ...&.zR.....0...
    94 f4 a7 01 8e 28 c5 00 33 39 e3 14 f0 bc 51 81    .....(..39....Q.
    4f 5a 4d d8 ab a1 70 31 d2 93 14 ea 70 a9 72 4d    OZM...p1....p.rM
    09 bb 91 95 e3 35 11 5e f5 65 c7 6a 84 d0 52 d8    .....5.^.e.j..R.
    86 8c 53 88 a4 a3 70 d8 4c 51 8a 0d 19 a7 61 5d    ..S...p.LQ....a]
    09 9a 42 68 c5 18 ad ce 30 cd 2e 69 31 48 7b 9a    ..Bh....0..i1H{.
    00 76 69 69 9d 69 73 41 2d b1 d9 a7 03 9a 65 28    .vii.isA-.....e(
    a0 b2 5a 33 4c dd ed 46 7d a8 1d d9 28 6a 5c d3    ..Z3L..F}...(j\.
    17 9a 76 3d ea 5e e3 5a 8e a2 92 96 9d 90 3d 84    ..v=.^.Z......=.
Cleaned 4 remaining connection(s) from connection pool

┌──(min㉿WIN-U49VUBQG3G3)-[~/forensic/webnet1]
└─$
```
y asi obtenemos la bandera: picoCTF{honey.roasted.peanuts}
## Notas
- 
## Referencias
- 