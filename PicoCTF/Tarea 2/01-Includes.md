## Includes

## Descripcion
Can you get the flag? Go to this [website](http://saturn.picoctf.net:51594/) and see what you can discover.
## Solucion
si revisamos el codigo fuente de la pagina vemos que en el archivo de estilos .css se encuentra la primera mitad de la bandera
```
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
```
si revisamos el javascript de la pagina encontraremos la otra mitad de la bandera
```
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}
```
## Notas
- la bandera completa es: picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}
## Referencias
- 