## Local Authority

## Descripcion
Can you get the flag? Go to this [website](http://saturn.picoctf.net:64350/) and see what you can discover.
## Solucion
Si entramos a la pagina del reto vemos que hay un formulario para iniciar sesion en la pagina, ponemos cualquier dato y nos sale que login failed, revisando con burp en el historial revise la request del login y me encontre con que la validacion del usuario y contraseña la hacen mediante el archivo secure.js asi que revisamos ese script
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
y nos encontramos con que el usuario es admin y la contraseña es strongPassword098765
hacemos login con estos datos y obtenemos la bandera:
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
## Notas
- 
## Referencias
- 