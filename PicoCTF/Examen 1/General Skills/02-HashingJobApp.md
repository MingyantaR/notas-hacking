## Descripcion
If you want to hash with the best, beat this test! `nc saturn.picoctf.net 53914`
## Solucion
para este reto al conectarnos al servidor nos pide que saquemos el hash md5 de las palabras que nos da, esto lo podemos hacer con un comando:
echo -n "palabra" | md5sum, el -n lo ponemos para que no haga saltos de linea y nos de el hash completo

use 2 terminales 1 para responder en el servidor del reto y otra para sacar el hash de una con el comando:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc saturn.picoctf.net 53914
Please md5 hash the text between quotes, excluding the quotes: 'Clark Gable'
Answer:
e4cfcc510ba955ce7e3458a9a88bb450
e4cfcc510ba955ce7e3458a9a88bb450
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'grave robbers'
Answer:
bf48d2ac4e5d0532912c8e8e0998645f
bf48d2ac4e5d0532912c8e8e0998645f
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'school cafeteria'
Answer:
3e06bd96dca5d429a2e06b3ea613eb41
3e06bd96dca5d429a2e06b3ea613eb41
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_3eb82b73}

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$

```

```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ echo -n "Clark Gable" | md5sum
e4cfcc510ba955ce7e3458a9a88bb450  -

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ echo -n "grave robbers" | md5sum
bf48d2ac4e5d0532912c8e8e0998645f  -

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ echo -n "school cafeteria" | md5sum
3e06bd96dca5d429a2e06b3ea613eb41  -

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$

```
## Notas
- 
## Referencias
- 