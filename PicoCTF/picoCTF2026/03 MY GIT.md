MY GIT

Description
I have built my own Git server with my own rules! 
You can clone the challenge repo using the command below. 
git clone ssh://git@foggy-cliff.picoctf.net:50489/git/challenge.git 
Here's the password: 4f7061f2 
Check the README to get your flag!

Solución 

```
fergll@FerGLl:/mnt/c/Users/ferch/documents/challenge$ git push origin master
git@foggy-cliff.picoctf.net's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 20 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 279 bytes | 55.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: Author matched and flag.txt found in commit...
remote: Congratulations! You have successfully impersonated the root user
remote: Here's your flag: picoCTF{1mp3rs0n4t4_g17_345y_220a9833}
To ssh://foggy-cliff.picoctf.net:50489/git/challenge.git
   0dcb7df..e7de732  master -> master

```

picoCTF{1mp3rs0n4t4_g17_345y_220a9833}

Notas adicionales

Validación Débil: El servidor Git del reto estaba configurado para confiar en los metadatos del commit (user.name y user.email)
Servidor con Hooks: Cuando se realizo el git push, el servidor ejecutó un script automático que decía algo como: "Si el autor es 
root@picoctf y el archivo flag.txt está presente, imprime la flag en la consola".
Identidad SSH vs. Identidad Git: se utilizo la clave SSH para conectarte (el canal), pero se uso la configuración de Git para identificarte 
(el autor). El servidor validó el autor, no quién estaba detrás de la conexión.

Referencias
