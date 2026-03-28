## Descripcion
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer. `ssh -p 53625 ctf-player@saturn.picoctf.net`. The password is `d137d16e`
## Solucion
al abrir el reto, comandos como ls, cat, whoami, etc no funcionan entonces si presionamos dos veces tab podemos ver los comandos que el sistema nos deja usar
```
Specialer$
!          cd         else       hash       pwd        times
./         command    enable     help       read       trap
:          compgen    esac       history    readarray  true
[          complete   eval       if         readonly   type
[[         compopt    exec       in         return     typeset
]]         continue   exit       jobs       select     ulimit
alias      coproc     export     kill       set        umask
bash       declare    false      let        shift      unalias
bg         dirs       fc         local      shopt      unset
bind       disown     fg         logout     source     until
break      do         fi         mapfile    suspend    wait
builtin    done       for        popd       test       while
caller     echo       function   printf     then       {
case       elif       getopts    pushd      time       }
Specialer$
```

entonces con pwd vemos en que directorio estamos, si salimos de este directorio y ponemos el comando de cambiar directorio junto con el directorio en el que estabamos, es decir cd ctf-player y damos 2 veces tab nos intentara autocompletar y mostrara los demas directorios que hay:
```
Specialer$ cd abra/cada
cadabra.txt   cadaniel.txt
Specialer$ cd abra/cada
-bash: cd: abra/cada: No such file or directory
Specialer$ cd abra
Specialer$ cd cada
cadabra.txt   cadaniel.txt
Specialer$ cd cada
cadabra.txt   cadaniel.txt
Specialer$ cd cada
-bash: cd: cada: No such file or directory
Specialer$ echo $(<cadabra.txt)
Nothing up my sleeve!
Specialer$ echo $(<cadaniel.txt)
Yes, I did it! I really did it! I'm a true wizard!
Specialer$ cd ..
Specialer$ cd ala/
kazam.txt  mode.txt
Specialer$ cd ala/
Specialer$ echo $(<kazam.txt)
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_838b49d1}
Specialer$
```
de esta manera revisando los diversos directorios que tiene el reto al abrir el archivo kazam.txt encontraremos la bandera:picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_838b49d1}
## Notas
- 
## Referencias
- 