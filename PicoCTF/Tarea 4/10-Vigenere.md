## Descripcion
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/160/cipher.txt) using this key "CYLAB".
## Solucion
revisando el archivo del texto obtenemos esto:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/tarea4]
└─$ cat cipher.txt
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}
```
entonces como indica el nombre del reto la bandera esta cifrada con el metodo vigenere, usando esta [pagina](https://www.dcode.fr/vigenere-cipher) podemos obtener la bandera usando la clave que nos da el mismo reto:
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}
## Notas
- 
## Referencias
- 