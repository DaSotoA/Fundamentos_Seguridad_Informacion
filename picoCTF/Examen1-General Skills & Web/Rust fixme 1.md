### Rust fixme 1
### Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!
Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
### Solucion
- El usuario debe preparar su entorno instalando Rust (por ejemplo, mediante el script `rustup` indicado en el artículo) y navegar hacia el directorio del proyecto descargado (`/tmp/rust_proj`).
- El participante ejecuta el comando `cargo build` para intentar compilar el código. El compilador detendrá el proceso y arrojará tres mensajes de error detallados señalando las líneas conflictivas en el archivo `main.rs`.
- El usuario identifica el primer error en la línea 5: falta un delimitador al final de la instrucción. Se debe añadir un punto y coma para que la sintaxis sea válida:
	- **Original:** `let key = String::from("CSUCKS")`
    - **Corregido:** `let key = String::from("CSUCKS");`
- El usuario localiza el segundo error en la línea 18, originado por una palabra reservada mal escrita dentro de la condicional `if res.is_err()`. Se debe utilizar la instrucción correcta para retornar:
    - **Original:** `ret;`
    - **Corregido:** `return;`
- El participante revisa el tercer error en la línea 25, donde el formateador de la macro de impresión es inválido. Se debe sustituir por el formato estándar que permite a `println!` imprimir la variable desencriptada:
    - **Original:** `":?"`
    - **Corregido:** `"{}"`
- Con los tres errores solucionados, el usuario ejecuta el comando `cargo run`. El proyecto compilará exitosamente y la terminal imprimirá el resultado final: `picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}`.
### Notas
### Referencias