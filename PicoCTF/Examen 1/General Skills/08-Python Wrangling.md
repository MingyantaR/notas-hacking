## Descripcion
Python scripts are invoked kind of like programs in the Terminal... Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/2946b2b767f2d6792cb13dcfc9312c0fd5888dcabaf4196f2d88ae6d46f2a62c/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/2946b2b767f2d6792cb13dcfc9312c0fd5888dcabaf4196f2d88ae6d46f2a62c/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/2946b2b767f2d6792cb13dcfc9312c0fd5888dcabaf4196f2d88ae6d46f2a62c/flag.txt.en)?
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat ende.py

import sys
import base64
from cryptography.fernet import Fernet



usage_msg = "Usage: "+ sys.argv[0] +" (-e/-d) [file]"
help_msg = usage_msg + "\n" +\
        "Examples:\n" +\
        "  To decrypt a file named 'pole.txt', do: " +\
        "'$ python "+ sys.argv[0] +" -d pole.txt'\n"



if len(sys.argv) < 2 or len(sys.argv) > 4:
    print(usage_msg)
    sys.exit(1)



if sys.argv[1] == "-e":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "rb") as f:
        data = f.read()
        data_c = c.encrypt(data)
        sys.stdout.write(data_c.decode())


elif sys.argv[1] == "-d":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "r") as f:
        data = f.read()
        data_c = c.decrypt(data.encode())
        sys.stdout.buffer.write(data_c)


elif sys.argv[1] == "-h" or sys.argv[1] == "--help":
    print(help_msg)
    sys.exit(1)


else:
    print("Unrecognized first argument: "+ sys.argv[1])
    print("Please use '-e', '-d', or '-h'.")


┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat password.txt
720b6ad346f84cd483c60c7464dd95d4

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat flag.txt.en
gAAAAABpRaHLJvQHNKx7S5bkBbCbLRygnKBNN2x32PTowWwOk2iIsCAgGdGgp_g-lIbghg4z6VSdljq5-moyXGu-5aQcrz5iaUEjHJWDAvd2xSZCeNVfUSJoUfj_wuZyjP3gQB5LdglQ
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python ende.py -d flag.txt.en
Please enter the password:720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$
```
## Notas
al revisar los 3 programas con un cat pudimos ver que el script ocupaba argumentos especificos para darnos la bandera, -d para desencriptar y el arcjivo flag.txt.en que contiene la llave para revertir el cifrado, despues de ejecutar el script con esos argumentos, nos pide la contraseña del password.txt, la ponemos y obtenemos la bandera
## Referencias
- 