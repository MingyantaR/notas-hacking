## Collaborative Development

## Descripcion
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/71/challenge.zip)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ cat flag.py
print("Printing the flag...")

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ sudo nano flag.py
[sudo] password for min:

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git log
commit 6ce09adec311b859780caf89d993c58e34b53fa6 (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:51 2024 +0000

    init flag printer

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git checkout

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git checkout feature/part-1
Switched to branch 'feature/part-1'

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 min min 4096 Feb 21 18:26 .
drwxr-xr-x 3 min min 4096 Feb 21 18:23 ..
-rw-r--r-- 1 min min   64 Feb 21 18:26 flag.py
drwxr-xr-x 8 min min 4096 Feb 21 18:26 .git

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git log
commit 74ae5215b93a82ddf3dd37df3d4c6b5aff0a93ed (HEAD -> feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:51 2024 +0000

    add part 1

commit 6ce09adec311b859780caf89d993c58e34b53fa6 (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:51 2024 +0000

    init flag printer

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git checkout feature/part-2
Switched to branch 'feature/part-2'

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')
┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git log
commit b4612c914d8461d1b1a50652cc303b76813ee142 (HEAD -> feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:51 2024 +0000

    add part 2

commit 6ce09adec311b859780caf89d993c58e34b53fa6 (main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:51 2024 +0000

    init flag printer

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ git checkout feature/part-3
Switched to branch 'feature/part-3'

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$ cat flag.py
print("Printing the flag...")

print("w0rk_4c24302f}")

┌──(min㉿WIN-U49VUBQG3G3)-[~/T107_CollaDev/drop-in]
└─$
```
## Notas
- al ver el archivo descomprimido del zip del reto vemos que es un repositorio con un script para imprimir la bandera
- el main solo tiene una linea de codigo pero si checamos las demas ramas del repositorio veremos que podemos completar la bandera si revisamos el script de cada rama:
  part1= picoCTF{t3@mw0rk_
  part2 = m@k3s_th3_dr3@m_
  part3 = w0rk_4c24302f}
- bandera completa: picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}
## Referencias
- 