## Descripcion
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/127/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/c4]
└─$ cat message.txt
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140
┌──(min㉿WIN-U49VUBQG3G3)-[~/c4]
└─$ sudo nano basicmod1.py

┌──(min㉿WIN-U49VUBQG3G3)-[~/c4]
└─$ python basicmod1.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
128   - 17    - R
322   - 26    - 0
353   - 20    - U
235   - 13    - N
336   - 3     - D
73    - 36    - _
198   - 13    - N
332   - 36    - _
202   - 17    - R
285   - 26    - 0
57    - 20    - U
87    - 13    - N
262   - 3     - D
221   - 36    - _
218   - 33    - 7
405   - 35    - 9
335   - 2     - C
101   - 27    - 1
256   - 34    - 8
227   - 5     - F
112   - 1     - B
140   - 29    - 3

R0UND_N_R0UND_79C18FB3
```

script:
```
# leemos el mensaje y quitamos espacios y dividimos en partes
data = open('message.txt','r').read().strip().split(' ')

print(data)
flag = ''

# recorremos el mensaje para decodificarlo
for c in data:
        char = int(c) % 37
        print(f'{c:<5} - {char:<5} - ',end='')
         # mapeamos a letras en codigo ascii sumando 65
        if char>=0 and char<=25:
                s = chr(char+65)
        # mapeamos a numeros en codigo ascii (48 - 26)
        elif char>=26 and char<=35: 
                s= chr(char+22)
        elif char==36:
                s = '_'
        flag += s
        print(s)
print(f'\n{flag}')
```
## Notas
- descargamos el archivo del reto, lo revisamos y vemos que viene lo que parece un mensaje encriptado, el reto nos dice como podremos resolverlo
- entonces con el script de python que use recorre el mensaje y lo decodifica mapeando las letras a codigo ascii sumando 65
- despues mapea los numeros en codigo ascii de entre 48 a 26 y obtenemos la bandera: picoCTF{R0UND_N_R0UND_79C18FB3}
## Referencias
- 