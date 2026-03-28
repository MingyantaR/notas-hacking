Password Profiler

Description
We intercepted a suspicious file from a system, but instead of the password 
itself, it only contains its SHA-1 hash. Using OSINT techniques, you are provided 
with personal details about the target. Your task is to leverage this information 
to generate a custom password list and recover the original password by 
matching its hash. 
Download the following files: 
userinfo: Contains the personal details. 
hash: Contains the SHA-1 hash of the password. 
check_password: Script to test passwords against the hash.

Solución 

fergll@FerGLl:/mnt/c/Users/ferch/documents/Password$ python3 check_password.py
Password found: picoCTF{Aj_15901990}

Notas adicionales

OSINT y Preparación: cat userinfo (para extraer los nombres y fechas de Alice) y git clone https://github.com/Mebus/cupp.git (para obtener la herramienta).
Generación del Diccionario: python3 cupp.py -i (donde ingresaste los datos para crear las 29,660 combinaciones).
Organización de Archivos: mv alice.txt .. y cd .. (para mover el diccionario a la carpeta del script).
Ajuste de Compatibilidad: mv alice.txt passwords.txt (para que el script encontrara el nombre de archivo exacto que esperaba).
Ataque de Hash: python3 check_password.py (para comparar el hash SHA-1 contra tu lista y revelar la contraseña).

Referencias
