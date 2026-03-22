## Based

## Descripcion
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?
nc fickle-tempest.picoctf.net 63674
## Solucion
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ nc fickle-tempest.picoctf.net 63674
Let us see how data is stored
lamp
Please give the 01101100 01100001 01101101 01110000 as a word.
...
you have 45 seconds.....
https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDExMDAgMDExMDAwMDEgMDExMDExMDEgMDExMTAwMDA
Input:
lamp
Please give me the  o163 o164 o162 o145 o145 o164 as a word.
https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTYzIDE2NCAxNjIgMTQ1IDE0NSAxNjQ&oeol=FF
Input:
street
Please give me the 6c697a617264 as a word.
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NmM2OTdhNjE3MjY0
Input:
lizard
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_aa2bA794}
## Notas
- El reto se resolvio convirtiendo entre diferentes bases a su equivalente en ascii
- Binario a ascii
- Octal a ascii
- Hexa a ascii
## Referencias
- https://gchq.github.io/CyberChef/