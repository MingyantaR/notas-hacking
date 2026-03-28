## Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
## Solucion
descargamos y descomprimimos el archivo del reto, nos da una carpeta de un proyecto de rust:
```
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
```
revisando el codigo, ahi mismo comentado nos dice pistas de los errores:
```
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS") // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", ">
    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        ret; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        ":?", // How do we print out a variable in the println function?
        String::from_utf8_lossy(&decrypted_buffer)
    );
}
```
- el 1ero how do we end statements in rust? es con ; al final
- el 2do how do we return in rust? para retornar es con return;
- el 3ro how do we print out a varuable in the println function? para imprimir un valor normal se usa {} y en el codigo esta :? que es el formato de debug, para que funcione debe ser {}
hacemos los cambios con nano y lo ejecutamos con cargo:
```
┌──(min㉿WIN-U49VUBQG3G3)-[~/fixme1/src]
└─$ cargo run main.rs
    Updating crates.io index
  Downloaded xor_cryptor v1.2.3
  Downloaded crossbeam-epoch v0.9.18
  Downloaded crossbeam-deque v0.8.5
  Downloaded either v1.13.0
  Downloaded crossbeam-utils v0.8.20
  Downloaded rayon-core v1.12.1
  Downloaded rayon v1.10.0
  Downloaded 7 crates (379.2KiB) in 2.12s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/min/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 22.14s
     Running `/home/min/fixme1/target/debug/rust_proj main.rs`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

┌──(min㉿WIN-U49VUBQG3G3)-[~/fixme1/src]
└─$
```
y asi obtenemos la bandera: picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
## Notas
- 
## Referencias
- 