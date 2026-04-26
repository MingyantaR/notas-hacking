## Descripcion
This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat: `$ nc verbal-sleep.picoctf.net 58932` The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/68dea6cb63f53886d85611943a2abf0c22e38ce960966417f393cd053daee689/encrypt.py).
## Solucion
nos conectamos al reto y obtenemos estos valores
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/tarea4]
└─$ nc verbal-sleep.picoctf.net 58932
N: 19124587442587049905570240318056733368232409461511582309211660684079491681350285180092034148038710195819532728656461888355333715102026706258624547280800278
e: 65537
cyphertext: 14572942525282469963111935898001849364321530902825487580690332443811275699433289002045439611284897636914275935962787040374303251106798318757529641773119761
```
si vemos la N observamos que los valores son mayormente valores impares, lo que es inusual ya que usualmente n siempre deberia ser par, con esta sospecha podemos probar este script:
```
from Crypto.Util.number import long_to_bytes

N = 19124587442587049905570240318056733368232409461511582309211660684079491681350285180092034148038710195819532728656461888355333715102026706258624547280800278
e = 65537

q = N // 2
phi_N = q - 1
d = pow(e, -1, phi_N)

c = 14572942525282469963111935898001849364321530902825487580690332443811275699433289002045439611284897636914275935962787040374303251106798318757529641773119761

m = pow(c, d, N)
flag = long_to_bytes(m)
print(flag)
```
y obtenemos la bandera:
picoCTF{tw0_1$_pr!m3df98b648}
## Notas
- 
## Referencias
- 