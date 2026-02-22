## binhexa

## Descripcion
How well can you perfom basic binary operations? Start searching for the flag here `nc titan.picoctf.net 50763`
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc titan.picoctf.net 50763

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11101100
Binary Number 2: 01011110


Question 1/6:
Operation 1: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0101001010
Incorrect. Try again
Enter the binary result: 0101011010101000
Correct!

Question 2/6:
Operation 2: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0101001010
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1110110001011110
Incorrect. Try again
Enter the binary result: 01001100
Correct!

Question 4/6:
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111110
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 11011000
Incorrect. Try again
Enter the binary result: 10111100
Incorrect. Try again
Enter the binary result: 11011000
Incorrect. Try again
Enter the binary result: 11011000
Incorrect. Try again
Enter the binary result: 111011000
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00101111
Correct!

Enter the results of the last operation in hexadecimal: 2F

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$
```
## Notas
- el reto fue sencillo, solo era a partir de los 2 numeros en binario que nos da hacer las distintas operaciones que nos va pidiendo
- La operacion 3 fue & es decir es una operacion AND en la que el resultado es 1 solo si en ambos bits hay un 1
```
|**A**|       |**B**|      |**C**|
|**0**|**AND**|**0**|**->**|**0**|
|**0**|**AND**|**1**|**->**|**0**|
|**1**|**AND**|**0**|**->**|**0**|
|**1**|**AND**|**1**|**->**|**1**|
```
- La operacion 4 es una operacion OR en donde el resultado es 1 si al menos uno de los 2 bits es 1
```
|**A**|       |**B**|      |**C**|
|**0**|**AND**|**0**|**->**|**0**|
|**0**|**AND**|**1**|**->**|**1**|
|**1**|**AND**|**0**|**->**|**1**|
|**1**|**AND**|**1**|**->**|**1**|
```
- Las operaciones 5 y 6 son cambios de bit a la derecha e izquierda, se recorren una posicion el numero y se pone un 0 en el otro lado, por ejemplo en la 5 el numero es 11101100, se recorre a la izquierda y se agrega un 0 a la derecha 111011000
- y al final solo nos piden convertir el ultimo resultado a hexa y nos da la bandera: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_675602ae}
  
## Referencias
- http://www.xcprod.com/titan/XCSB-DOC/binary_and.html
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR
- https://www.interviewcake.com/concept/java/bit-shift