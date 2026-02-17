## runme.py

## Descripcion
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell. [Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ wget https://artifacts.picoctf.net/c/34/runme.py
--2026-02-13 16:19:03--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.125, 13.225.222.120, 13.225.222.105, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘runme.py’

runme.py                      100%[=================================================>]     270  --.-KB/s    in 0s

2026-02-13 16:19:04 (96.5 MB/s) - ‘runme.py’ saved [270/270]

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ python runme.py
picoCTF{run_s4n1ty_run}

```

## Notas
- Este reto fue otro simple, descargamos el script de python que nos da el reto, lo ejecutamos y nos da la bandera = picoCTF{run_s4n1ty_run}
## Referencias
- 