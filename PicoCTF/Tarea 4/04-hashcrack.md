## Descripcion
A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server? Access the server using `nc verbal-sleep.picoctf.net 57730`
## Solucion
al entrar a la direccion del reto observamos esto:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/tarea4]
└─$ nc verbal-sleep.picoctf.net 57730
Welcome!! Looking For the Secret?

We have identified a hash: 482c811da5d5b4bc6d497ffa98491e38
Enter the password for identified hash:
Incorrect. Goodbye.

```
podemos observar que nos dan un hash y parece ser un md5:
```
MD5- 32 characters

SHA 1- 40 characters

SHA 256- 65 characters
```
ya que contiene 32 caracteres, iremos a la pagina 10015.io en este caso el [MD5](https://10015.io/tools/md5-encrypt-decrypt) decrypt para ir desencriptando lo que nos da el reto:
en este caso el md5 fue password123
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc verbal-sleep.picoctf.net 57730
Welcome!! Looking For the Secret?

We have identified a hash: 482c811da5d5b4bc6d497ffa98491e38
Enter the password for identified hash: password123
Correct! You've cracked the MD5 hash with no secret found!
```
despues toco b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3 que es un SHA1, lo [desencriptamos](https://10015.io/tools/sha1-encrypt-decrypt) y obtenemos: letmein
```
Flag is yet to be revealed!! Crack this hash: b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
Enter the password for the identified hash: letmein
Correct! You've cracked the SHA-1 hash with no secret found!
```
ahora nos da esto: 916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
si lo [desencriptamos](https://10015.io/tools/sha256-encrypt-decrypt) obtenemos: qwerty098
```
Almost there!! Crack this hash: 916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
Enter the password for the identified hash: qwerty098
Correct! You've cracked the SHA-256 hash with a secret found.
```
y asi obtenemos la bandera:
```
The flag is: picoCTF{UseStr0nG_h@shEs_&PaSswDs!_93e052d7}
```

## Notas
- 
## Referencias
- 