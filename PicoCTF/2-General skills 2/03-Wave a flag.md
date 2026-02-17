## Reto

## Descripcion
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information... [warm](https://challenge-files.picoctf.net/c_wily_courier/70013ed41d4cfe2bb48628471dac6fc12238b5dbe164301ae3b4e35277b1e80b/warm)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ chmod +x ./warm
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```
picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
## Notas
- Usamos chmod +x ./warm para cambiarle el modo de acceso al archivo 
- Asi nos deja usar -h para como dice el reto invocar bandera de ayuda a una herramienta o ejecutable
## Referencias
