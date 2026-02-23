## Insp3ct0r

## Descripcion
Kishor Balan tipped us off that the following code may need inspection: http://fickle-tempest.picoctf.net:52738
## Solucion
el reto nos da una pagina, dice que la hizo con 3 cosas:
- HTML
- CSS
- JS(JavaScript)
esto nos da una pista, si revisamos el codigo fuente de la pagina nos da el primer tercio de la bandera:
- <!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
si revisamos mycss.css de la pagina nos encontramos con otro tercio de la bandera:
- You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t 
ahora revisamos el JavaScript y nos encontramos con la parte final de la bandera:
/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?302945a7} */
## Notas
- la bandera completa es: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?302945a7}
## Referencias
- 