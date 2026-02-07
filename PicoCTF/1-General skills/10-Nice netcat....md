## Nice netcat...

## Descripcion
There is a nice program that you can talk to by using this command in a shell: $ nc wily-courier.picoctf.net 52184, but it doesn't speak English...
## Solucion
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Line%20feed',false)&input=MTEyCjEwNQo5OQoxMTEKNjcKODQKNzAKMTIzCjEwMwo0OAo0OAoxMDAKOTUKMTA3CjQ5CjExNgoxMTYKMTIxCjMzCjk1CjExMAo0OQo5OQo1MQo5NQoxMDcKNDkKMTE2CjExNgoxMjEKMzMKOTUKMTAxCjU3Cjk5CjU2CjUzCjEyNQoxMA
picoCTF{g00d_k1tty!_n1c3_k1tty!_e9c85}
## Notas
- Al usar nc con las credenciales del reto nos regresa una serie de numeros
- Si los convertimos a su equivalente de ASCII obtendremos la bandera
## Referencias
- https://gchq.github.io/CyberChef/