## Irish-Name-Repo 1

## Descripcion
Do you think you can log us in? Try to see if you can login!

Additional details will be available after launching your challenge instance.
## Solucion
al entrar a la pagina del reto, debemos entrar como admin a la pagina pero nos sale error si ponemos cualquier cosa, si inspeccionamos la pagina y vemos en el boton de login vemos esta linea: input type="hidden" name="debug" value="0", debemos cambiar el valor de 0 a 1 para que nos deje ver masomenos como funciona el login de la pagina, y para poder acceder a la bandera como en el campo de login no hay nada que nos impida poner un texto erroneo podemos usar una vulnerabilidad de sql injection: SQL Injection Based on 1=1 is Always True, con esto podemos tener acceso a todos los nombres de usuario y contraseñas de una base de datos, asi ponemos en usuario y contraseña 'or 1=1; para que nos deje entrar y cuando le damos a login nos muestra la bandera 
## Notas
- 
## Referencias
- https://www.w3schools.com/sql/sql_injection.asp