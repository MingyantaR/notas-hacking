## Descripcion
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/3dced65f7a857f7a28f538da0f98fdceca989646f69d4651133b5c04590b0b0d/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/3dced65f7a857f7a28f538da0f98fdceca989646f69d4651133b5c04590b0b0d/scrambled2.png)
## Solucion
descargamos las 2 imagenes del reto, vemos que al parecer las imagenes contienen puros pixeles de colores random y ordenados al azar pero en realidad esto es una forma de enciptar informacion, se llama visual cryptography, entonces con la herramienta stegsolve podremos encontrar la bandera
abrimos la imagen 1, despues con la opcion analyse - image combiner abrimos la segunda y con las flechitas de la aplicacion buscamos la opcion que diga add y veremos clara la bandera:
picoCTF{8cdf93c3}
## Notas
- 
## Referencias
- 