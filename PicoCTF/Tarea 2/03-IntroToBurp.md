## IntroToBurp

## Descripcion
Try [here](http://titan.picoctf.net:58246/) to find the flag
## Solucion
entramos a la pagina del reto y rellenamos el formulario de registro con cualquier cosa, en mi caso puse 1 en todos los campos activamos el burpsuite y la extnesion de foxyproxy, le damos a la request post en el burpsuit y le damos forward hasta que cambie en el navegador, ahora pide una clave otp ponemos cualquier cosa y le damos al boton, ahora en burpsuite checamos la request con post y vemos que hasta abajo dice otp= y lo que le pusimos, lo borramos esa parte y le damos al forward, ahora quitamos la intercepcion y nos da el siguiente mensaje:
Welcome, 1 you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}
## Notas
- 
## Referencias
- 