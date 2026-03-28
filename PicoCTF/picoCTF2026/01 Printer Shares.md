Printer Shares

Description
Oops! Someone accidentally sent an important file to a network printer—can you retrieve it from the print server? 
The printer is on 50102. 
you can try $ nc -vz mysterious-sea.picoctf.net 50102

Solución 

picoCTF{5mb_pr1nter_5h4re5_9fc5e085}

Notas adicionales

Enumeración de SMB: Se utilizo smbclient -L para descubrir qué recursos compartidos estaban disponibles en el servidor remoto.

Acceso no autenticado (Null Session): se aprovecho una mala configuración que permitía entrar al recurso shares sin usuario ni contraseña.

Transferencia de Archivos: se navego por el sistema de archivos remoto y utilice el comando get para extraer el archivo sensible (flag.txt) hacia tu máquina local.

Referencias


