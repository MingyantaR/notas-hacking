## PW Crack 1

## Descripcion
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.
## Solucion
Al ejecutar el programa del reto nos da lo siguiente:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python level1.py
Please enter correct password for flag:
That password is incorrect
```
si revisamos la bandera encriptada vemos esto:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat level1.flag.txt.enc
[gE]__TgS^S

           J
```
si echamos un vistasillo rapido al codigo encontraremos la solucion:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat level1.py
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

```
la solucion es 8713, si le damos esos numeros al programa nos dara la bandera
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python level1.py
Please enter correct password for flag: 8713
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
```
## Notas
- 
## Referencias
- 