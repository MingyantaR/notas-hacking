## PW Crack 2

## Descripcion
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat level2.flag.txt.enc
D
 Vw1%B@W
        \:ZRWS:ZT
                 T
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat level2.py
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

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python
Python 3.13.9 (main, Oct 15 2025, 14:56:22) [GCC 15.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
'4ec9'
>>>
[3]+  Stopped                    python

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
```

## solucion 2

	print(chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39))
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
	imprime la contraseña y simplemente la introducimos cuando ejecutamos el programa
## Notas
- Este reto es como el de PW Crack 1, revisamos el programa del reto y vemos que ahora lo que pide es un texto en hexadecimal = chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
- Si eso lo convertimos a su equivalente en ASCII nos dara la clave 4ec9
- y al ejecutar el programa y dandole lo que obtuvimos del texto en hexa nos da la bandera = picoCTF{tr45h_51ng1ng_9701e681}
## Referencias
- 