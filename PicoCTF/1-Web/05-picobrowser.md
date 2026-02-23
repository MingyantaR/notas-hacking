## picobrowser

## Descripcion
This website can be rendered only by picobrowser, go and catch the flag! http://fickle-tempest.picoctf.net:61909
## Solucion
La pagina del reto nos presenta un boton que dice flag, si le damos click nos dara un mensaje que dice que no somos picobrowser, y nos muestra el user-agent de nuestro navegador, en mi caso firefox: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:147.0) Gecko/20100101 Firefox/147.0
pero si cambiamos el user-agent a picobrowser y le damos al boton nos dara la bandera:
`picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}`
## Notas
- El user-agent es un request header es una cadena que le deja a los servidores y a la red identificar la aplicacion, sistema operativo, proveedor y/o version de el user-agent solicitante
## Referencias
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/User-Agent