## dont-use-client-side

## Descripcion
Can you break into this super secure portal? http://fickle-tempest.picoctf.net:60762
## Solucion
La pagina del reto nos pone un cuadro de texto donde debemos poner una contraseña, si inspeccionamos la pagina y nos vamos a la seccion de Debugger, revisamos el archivo html vemos que hay una seccion donde la bandera esta fragmentada
<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == 'eb02') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_2') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'b45}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>
si revisamos este pedazo de codigo, vemos que separa de a 4 caracteres una cadena, el inicio de la bandera es donde esta el 0 == pico, despues split, split*2 == CTF{ y asi hasta que armamos la bandera completa: picoCTF{no_clients_plz_2eb02b45}
## Notas
- 
## Referencias
- 