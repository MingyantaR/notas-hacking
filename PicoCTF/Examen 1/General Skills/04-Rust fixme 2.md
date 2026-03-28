## Descripcion
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
## Solucion
en este reto al igual que el fixme1 hay que corregir una serie de errores en el codigo, estos son los cambios:
```
let mut party_foul = String::from("Using memory unsafe languages is a: ");

decrypt(encrypted_buffer, &mut party_foul);

fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String) {
```
ahora ejecutamos el main.rs del reto y obtendremos la bandera:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/fixme1/src/fixme2/src]
└─$ cargo run main.rs
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/min/fixme1/src/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 17.16s
     Running `/home/min/fixme1/src/fixme2/target/debug/rust_proj main.rs`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}
```
## Notas
- 
## Referencias
- 