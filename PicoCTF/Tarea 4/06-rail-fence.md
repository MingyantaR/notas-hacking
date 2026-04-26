## Descripcion
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://artifacts.picoctf.net/c/188/message.txt). Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.
## Solucion
el mensaje del reto es este:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat message.txt
Ta _7N6D49hlg:W3D_H3C31N__A97ef sHR053F38N43D7B i33___N6
```
con la siguiente [pagina](https://www.boxentriq.com/ciphers/rail-fence-cipher#manual) podremos obtener la bandera:
```
T     a           _     7     N     6     D     4     9 
 h   l g   : W   3 D   _ H   3 C   3 1   N _   _ A   9 7
  e f     s   H R   0 5   3 F   3 8   N 4   3 D   7 B   
         i     3     3     _     _     _     N     6
```
The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997
## Notas
- 
## Referencias
- ****