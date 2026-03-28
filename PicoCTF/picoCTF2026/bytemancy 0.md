## Descripcion
Can you conjure the right bytes? The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_candy_mountain/a50bbcde1dd7d8337a88235c9340de0f5f1482980fafa943a318859128f42672/app.py). Connect to the program with netcat: `$ nc candy-mountain.picoctf.net 60958`
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/retos]
└─$ nc candy-mountain.picoctf.net 60958
⊹──────[ BYTEMANCY-0 ]──────⊹
☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐

Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.

☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐
⊹─────────────⟡─────────────⊹
==> eee
picoCTF{pr1n74813_ch4r5_9b465df3}

┌──(min㉿WIN-U49VUBQG3G3)-[~/retos]
└─$
```
## Notas
- al conectarnos a donde nos dice el reto nos pide que le digamos los caracteres en ascii de los decimales correspondientes
- 101 en ascii es e entonces le mandamos eee
- nos da la bandera:picoCTF{pr1n74813_ch4r5_9b465df3}
## Referencias
- 