## chrono

## Descripcion
How to automate tasks to run at intervals on linux servers? Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 50035
Username: picoplayer 
Password: kZx-HVJKu8
```
## Solucion
```

picoplayer@challenge:/$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}
picoplayer@challenge:/$

```

## Notas
- cron es un servicio que se encarga de ejecutar tareas de forma automatica en fechas o intervalos de tiempo especificos
- cuando se ejecuta el comando cat /etc/crontab revisa el archivo de texto que define la agenda de tareas del sistema
## Referencias
- https://www.redhat.com/en/blog/linux-cron-command