### Rust fixme 2
### Descripcion
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?
Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
### Solucion
- Se descarga el archivo fuente y se intenta compilar usando el gestor de paquetes Cargo (`cargo run`), lo cual detendrá la ejecución arrojando errores relacionados con la mutabilidad y la sintaxis.
- En la función `main`, se identifica que la variable `party_foul` intenta ser modificada posteriormente, pero por defecto fue declarada como inmutable. Se debe corregir su declaración agregando la palabra reservada `mut`:
    - **Original:** `let party_foul = String::from("Using memory unsafe languages is a: ");`
    - **Corregido:** `let mut party_foul = String::from("Using memory unsafe languages is a: ");`
- Al invocar a la función `decrypt` desde `main`, se debe pasar la variable como una referencia mutable en lugar de una referencia inmutable estándar:
    - **Original:** `decrypt(encrypted_buffer, &party_foul);`
    - **Corregido:** `decrypt(encrypted_buffer, &mut party_foul);`
- Acorde a lo anterior, en la firma de la función `decrypt`, el parámetro que recibe la cadena de texto debe actualizarse para aceptar explícitamente dicha referencia mutable:
    - **Original:** `fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &String)`
    - **Corregido:** `fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String)`
- Por último, dentro de la misma función `decrypt`, se deben corregir tres errores de sintaxis heredados del reto anterior:
    - Añadir el punto y coma faltante al final de la declaración de la llave: `let key = String::from("CSUCKS");`.
    - Cambiar la palabra reservada incorrecta `ret;` por `return;` dentro de la evaluación de errores.
    - Corregir el formato de la macro de impresión en `println!` usando `"{}"` para poder mostrar la variable en consola.
- Una vez aplicadas todas las correcciones en el archivo, se ejecuta nuevamente el comando `cargo run`. El programa compilará sin advertencias e imprimirá el texto final junto con la bandera en la terminal.

picoCTF{4r3_y0u_h4v1n5_fun_y31?}
### Notas
### Referencias