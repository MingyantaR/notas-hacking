## Descripcion
This file doesn't look like much... just a bunch of 1s and 0s. But maybe it's not just random noise. Can you recover anything meaningful from this? Download the file [here](https://challenge-files.picoctf.net/c_plain_mesa/822de7c94de737c4126247e42823961976c10bd18e61eb56787d8c1e74c15f0d/digits.bin).
## Solucion
https://gchq.github.io/CyberChef/#recipe=From_Binary('None',8)
Al meter el archivo del reto en cyberchef y usar from binary vemos en output que sale JFIF esto me recuerda a que es una imagen, buscando bien que tipo de imagen es me encontre con que es un estandar de archivo de imagen basado en la compresion JPEG entonces le damos a la opcion de guardar salida a archivo en cyberchef y lo guardamos como .jpg entonces abrimos la imagen y nos encontramos con la bandera: picoCTF{h1dd3n_1n_th3_b1n4ry_2c2db635}
## Notas
- 
## Referencias
- 