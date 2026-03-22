MultiCode

Description
We intercepted a suspiciously encoded message, but it’s clearly hiding a flag. No 
encryption, just multiple layers of obfuscation. Can you peel back the layers and 
reveal the truth? Download the message.

Solución 

```

fergll@FerGLl:/mnt/c/Users/ferch/documents$ cat message.txt
NjM3NjcwNjI1MDQ3NTMyNTM3NDI2MTcyNjY2NzcyNzE1ZjcyNjE3MDMwNzE3NjYxNzQ1ZjczMzM2ZTMyMzQ3MzM3MzMyNTM3NDQ=
fergll@FerGLl:/mnt/c/Users/ferch/documents$ echo "NjM3NjcwNjI1MDQ3NTMyNTM3NDI2MTcyNjY2NzcyNzE1ZjcyNjE3MDMwNzE3NjYxNzQ1ZjczMzM2ZTMyMzQ3MzM3MzMyNTM3NDQ=" | base64 -d
637670625047532537426172666772715f72617030717661745f73336e3234733733253744fergll@FerGLl:/mnt/c/Users/ferch/documents$ echo "637670625047532537426172666772715f72617030717661745f73336e323echo "637670625047532537426172666772715f72617030717661745f73336e3234733733253744" | xxd -r -p
fergll@FerGLl:/mnt/c/Users/ferch/documents$ echo "cvpbPGS%7Barfgrq_rap0qvat_s3n24s73%7D" | sed 's/%7B/{/g; s/%7D/}/g' | tr 'A-Za-z' 'N-ZA-Mn-za-m'%7D/}/g' | tr 'A-Za-z' 'N-ZA-Mn-za-m'
picoCTF{nested_enc0ding_f3a24f73}

```

picoCTF{nested_enc0ding_f3a24f73}

Notas adicionales

Este reto es como una cebolla: la flag está envuelta en varias capas de encoding (codificación).
No hay criptografía real, solo transformación de datos.

Capa 1: Base64 (Texto con ==).

Capa 2: Hexadecimal (Números 6376...).

Capa 3: URL Encoding (Símbolos %7B).

Capa 4: ROT13 (Cifrado César de 13 posiciones).

Referencias
