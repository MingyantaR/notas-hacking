## where are the robots

## Descripcion
Can you find the robots? http://fickle-tempest.picoctf.net:51567
## Solucion
la pagina del reto nos da la bienvenida y nos dice puedes encontrar los robots?
en la barra de direcciones accedemos al archivo robots.txt de la pagina http://fickle-tempest.picoctf.net:51567/robots.txt
nos da una pagina no indexada a la que aun podemos acceder:
User-agent: *
Disallow: /cc6b1.html
http://fickle-tempest.picoctf.net:51567/cc6b1.html
y cuando entramos a esa pagina nos encontramos con este texto:
Guess you found the robots  
picoCTF{ca1cu1at1ng_Mach1n3s_cc6b1}
## Notas
- El archivo robots.txt es el que le indica a los rastreadores de los navegadores a que url del sitio pueden acceder 
## Referencias
- https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es