## Descripcion
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help UFJKXQZQUNB with the key of SOLVECRYPTO. Can you use this [table](https://challenge-files.picoctf.net/c_fickle_tempest/859ffc313a4d8b63149f144745043a7312fc4f993e405eeeb8ee5ae6ca8444a8/table.txt) to solve it?.
## Solucion
el cifrado vigenere esta basado en diferentes series de caracteres o letras del cifrado cesar formando estos caracteres una tabla usada como clave, usamos cyberchef como key damos SOLVECRPYTO y la bandera queda asi:
picoCTF{CRYPTOISFUN}
https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkI
## Notas
- 
## Referencias
- 