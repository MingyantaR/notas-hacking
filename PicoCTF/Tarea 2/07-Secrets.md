## Secrets

## Descripcion
We have several pages hidden. Can you find the one with the flag?
## Solucion
entramos a la pagina del reto, encontramos que la imagen esta en la ruta: secret/assets/DX1KYM.jpg
si entramos a /secret dice un mensaje
Finally. You almost found me. you are doing well

inspeccionando otra vez vemos que dice hidden/file.css 
entramos en secret/hidden y ahora tenemos una pantalla de login
si le damos datos cualesquiera nos da un mensaje:
Thank you for the attempt but oops! try harder. better luck next time
si inspeccionamos el boton de login nos sale un mensaje:
input type="hidden" name="db" value="superhidden/xdfgwd.html"
si ahora entramos a superhidden
vemos un mensaje

Finally. You found me. But can you see me
inspeccionando una ultima vez encontramos la bandera "oculta" ya que esta de color blanco:
### picoCTF{succ3ss_@h3n1c@10n_51b260fe}
## Notas
- 
## Referencias
- 