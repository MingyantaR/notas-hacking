## Logon

## Descripcion
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? http://fickle-tempest.picoctf.net:51879
## Solucion
la pagina del reto nos pide iniciar sesion como Joe pero no sabemos su contraseña, entonces probamos con otras credenciales y en este caso pusimos admin y admin tambien de contraseña para iniciar sesion, ya iniciamos sesion, pero no nos muestra la bandera aun, nos muestra un mensaje No flag for you, ahora si nos fijamos al inspeccionar el sitio, vemos que la cookie de nuestro inicio de sesion esta con el valor False, si ese valor lo cambiamos a True, la pagina ya nos va a mostrar la bandera `picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}`
## Notas
- 
## Referencias
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers
- https://policies.google.com/technologies/cookies?hl=es