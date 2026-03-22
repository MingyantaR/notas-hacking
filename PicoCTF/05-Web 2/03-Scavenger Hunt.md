## Scavenger Hunt

## Descripcion
There is some interesting information hidden around this site. Can you find it? http://wily-courier.picoctf.net:51936/
## Solucion
entramos al codigo fuente de la pagina del reto y en el .html encontramos la primera parte de la bandera: <!-- Here's the first part of the flag: picoCTF{t -->
si entramos al la hoja de estilos encontramos la 2da parte de la bandera:  CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 
si entramos al javascript de la pagina nos da un mensaje:  How can I keep Google from indexing my website?
si recordamos uno de los retos anteriores en donde revisabamos el robots.txt nos da otra parte de la bandera y otro mensaje:
 Part 3: t_0f_pl4c
 I think this is an apache server... can you Access the next flag?
 entramos al archivo .htaccess del servidor apache y nos da otra parte de la bandera y otro mensaje:
 # Part 4: 3s_2_lO0k
 I love making websites on my Mac, I can Store a lot of information there.
 entramos al archivo .DS_Store de la pagina y nos da la ultima parte: 
 Congrats! You've completed the scavenger hunt! Part 5: _9588550}
 

## Notas
- los servidores apache son una alternativa para hospedar paginas web, hay un archivo especial que se llama htaccess 
- hay un archivo llamado .DS_Store en donde se guarda la configuracion de vista de iconos y tambien que archivos hay en esa carpeta
- la bandera completa es: picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}
## Referencias
- 