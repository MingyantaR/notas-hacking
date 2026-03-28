## Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).
## Solucion
descomprimimos el archivo del reto y revisamos el programa main.rs con nano, el objetivo del reto es que sobrepasemos la seguridad de rust al usar raw pointers, debemos usar unsafe{} que es como una directiva para el compilador, y lo que hace es habilitar 5 capacidades prohibidas en el safe rust:
- desreferenciar raw pointers
- llamar a funciones marcadas como unsafe, es decir no tendra chequeos de seguridad en tiempo de ejecucion
- acceder o modificar variables estaticas mutables
- implementar traits inseguros 
- y acceder a campos de una union
entonces descomentamos lo de unsafe{} en el codigo y compilamos para que nos de la bandera:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/fixme3/src]
└─$ cargo run main.rs
   Compiling rust_proj v0.1.0 (/home/min/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 2.46s
     Running `/home/min/fixme3/target/debug/rust_proj main.rs`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
```
## Notas
- 
## Referencias
- 