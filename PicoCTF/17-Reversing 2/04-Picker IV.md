## Descripcion
Can you figure out how this program works to get the flag? Connect to the program with netcat: `$ nc saturn.picoctf.net 50700` The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/529/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/529/picker-IV).
## Solucion
en este reto debemos revisar que direccion tiene la funcion win, esto lo podemos hacer con gdb una herramienta de debug para revisar programas
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ gdb picker-IV
GNU gdb (Debian 17.1-3) 17.1
Copyright (C) 2025 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from picker-IV...
(No debugging symbols found in picker-IV)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000401000  _init
0x00000000004010e0  putchar@plt
0x00000000004010f0  puts@plt
0x0000000000401100  fclose@plt
0x0000000000401110  printf@plt
0x0000000000401120  fgetc@plt
0x0000000000401130  signal@plt
0x0000000000401140  setvbuf@plt
0x0000000000401150  fopen@plt
0x0000000000401160  __isoc99_scanf@plt
0x0000000000401170  exit@plt
0x0000000000401180  sleep@plt
0x0000000000401190  _start
0x00000000004011c0  _dl_relocate_static_pie
0x00000000004011d0  deregister_tm_clones
0x0000000000401200  register_tm_clones
0x0000000000401240  __do_global_dtors_aux
0x0000000000401270  frame_dummy
0x0000000000401276  print_segf_message
0x000000000040129e  win
0x0000000000401334  main
0x00000000004013d0  __libc_csu_init
--Type <RET> for more, q to quit, c to continue without paging--q
❌️ Quit
(gdb) quit
```
una vez que ya sabemos la direccion podemos conectarnos al servidor y obtener la bandera con la direccion de la funcion win:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc saturn.picoctf.net 50700
Enter the address in hex to jump to, excluding '0x': 0x40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_b8de1af4}
```
## Notas
- 
## Referencias
- 