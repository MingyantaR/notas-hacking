## MatchTheRegex

## Descripcion
How about trying to match a regular expression The website is running [here](http://saturn.picoctf.net:50310/).
## Solucion
Al entrar a la pagina del reto nos pide que metamos un texto, pero por ejemplo le damos pico y nada, al revisar un poco el codigo fuente vemos esto:
```
function send_request() { 
	let val = document.getElementById("name").value; 
	// ^p.....F!? 
	fetch(`/flag?input=${val}`) 
		.then(res => res.text()) 
		.then(res => { 
			const res_json = JSON.parse(res); 
			alert(res_json.flag) 
			return false; 
		}) 
	return false; 
}
```
y este codigo al parecer es el que valida la expresion regular
entramos a la siguiente pagina: https://regexr.com/
en la que nos explica como funciona la expresion regular en la pagina le pegamos esto: ^p.....F!? 
y la pagina nos explica como funciona esta regla de expresion regular, ^quiere decir que corresponde al inicio del string, despues la p es que la string empieza con una p, los puntos indican que corresponde a cualquier caracter excepto a un salto de linea, despues indica que la string termina con F! el signo de pregunta nos dice que corresponde entre 0 y 1 del token precedente, entonces si escribimos por ejemplo p12345F esto hace un match con la expresion regular, si la metemos a la pagina del reto nos da un mensaje con la bandera:picoCTF{succ3ssfully_matchtheregex_2375af79}
## Notas
- una expresion regular es una secuencia de caracteres que actua como modelo para la coincidencia y manipulacion de series.
## Referencias
- https://www.ibm.com/docs/es/i/7.5.0?topic=expressions-regular
- https://regexr.com/