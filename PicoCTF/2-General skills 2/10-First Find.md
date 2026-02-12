## First Find

## Descripcion
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/502/files.zip)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ find . -name "uber-secret.txt"
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cd files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/

┌──(min㉿WIN-U49VUBQG3G3)-[~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ cat uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}
```
## Notas
- al descomprimir el archivo del reto nos da una serie de archivos y directorios
- el comando find nos permite buscar archivos o directorios basados en el nombre, tipo, tamaño, fecha o otras condiciones
- si usamos find para encontrar el archivo "uber-secret.txt", veremos que esta dentro de ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
- si entramos al directorio y usamos cat para ver que contiene ese archivo encontraremos la bandera=picoCTF{f1nd_15_f457_ab443fd1}
## Referencias
- 