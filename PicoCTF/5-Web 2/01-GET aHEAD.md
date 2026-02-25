## GET aHEAD

## Descripcion
Find the flag being held on this server to get ahead of the competition http://wily-courier.picoctf.net:55288/
## Solucion
Inspeccionamos la pagina y nos vamos al apartado de network, ahi presionamos uno de los botones en mi caso el azul, en el primero que nos aparece con el metodo POST nos vamos donde dice resend y cambiamos el metodo a HEAD, lo enviamos y nos da la bandera en donde estan los response headers: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
## Notas
- 
## Referencias
- 