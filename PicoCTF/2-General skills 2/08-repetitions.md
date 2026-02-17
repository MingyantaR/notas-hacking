## repetitions

## Descripcion
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/472/enc_flag).
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKeldWaHdRMDB4V2tWU2JFNVdDbUpXV2tkVU1WcFhWVzFHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag|base64 -d
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JzWVhwQ00xWkVSbE5WCmJWWkdUMVpXVW1GdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag|base64 -d|base64-d
base64-d: command not found

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag|base64 -d|base64 -d
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFUd3BsYXpCM1ZERlNV
bVZGT1ZWUmFteEVXbm93T1VOblBUMEsK

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag|base64 -d|base64 -d|base64 -d
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aTwplazB3VDFSUmVFOVVRamxEWnowOUNnPT0K

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag|base64 -d|base64 -d|base64 -d|base64 -d|base64 -d
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfNzM0OTQxOTB9Cg==

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cat enc_flag|base64 -d|base64 -d|base64 -d|base64 -d|base64 -d |base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_73494190}
```
## Notas
- al revisar el archivo que nos da el reto con un cat podemos observar que se trata de un mensaje codificado en base64
- si lo decodificamos una vez, otra vez nos presenta un mensaje codificado en base64
- decodificando el mensaje hasta que ya no se pueda nos encontramos con la bandera=picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_73494190}
## Referencias