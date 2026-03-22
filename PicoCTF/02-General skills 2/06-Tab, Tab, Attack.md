## Tab, Tab, Attack

## Descripcion
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames. [Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
 extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/

┌──(min㉿WIN-U49VUBQG3G3)-[~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c

┌──(min㉿WIN-U49VUBQG3G3)-[~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}
```
## Notas
- extraemos el archivo del reto, son una serie de carpetas una dentro de otra
- entramos hasta la ultima carpeta y vemos que hay 2 archivos
- si ejecutamos fang-of-haynekhtnamet obtenemos la bandera
## Referencias
