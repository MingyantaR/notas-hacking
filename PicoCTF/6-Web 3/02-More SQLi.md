## More SQLi

## Descripcion
Can you find the flag on this website. Try to find the flag [here](http://saturn.picoctf.net:54220/).
## Solucion
entramos a la pagina como en el reto anterior poniendo en usuario y contraseña 'or 1=1;
despues nos muestra una barra de busqueda, en sqlite la tabla maestra es donde se guardan todos los nombres de las tablas y esta se llama sqlite_master. entonces en la barra de busqueda ponemos esto: 'UNION SELECT 1, sql, 3 FROM sqlite_master -- y nos muestra 4 tablas hints, more_table, offices y users, ahora revisando vemos que more tables tiene flag, revisamos el campo flag de la tabla more_tables: ' UNION SELECT 1, flag, 3 FROM more_table -- y nos da la bandera picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8ee9477}
## Notas
- 
## Referencias
- 