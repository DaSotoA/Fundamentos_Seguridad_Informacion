### Rust fixme 3
### Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!
Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).
### Solucion
1. Se descarga y extrae el archivo comprimido que contiene el código fuente del proyecto.
2. Al intentar compilar el código utilizando el comando `cargo build`, el compilador detendrá la ejecución arrojando un error. El mensaje indicará que se está realizando una llamada a una función insegura (_unsafe function_) sin el bloque de autorización correspondiente.
3. Se identifica la línea problemática en el código, la cual intenta construir una porción de memoria (_slice_) a partir de punteros crudos:
    - **Original:** `let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);`
4. Dado que la función `from_raw_parts` manipula punteros directamente, el compilador de Rust no puede garantizar por sí solo que dicha operación sea segura. Se debe corregir el código envolviendo explícitamente la ejecución de la función dentro de un bloque `unsafe {}`:
    - **Corregido:** `let decrypted_slice = unsafe { std::slice::from_raw_parts(decrypted_ptr, decrypted_len) };`
5. Una vez guardado el cambio, se ejecuta el comando `cargo run` en la terminal. El proyecto compilará sin inconvenientes y arrojará la bandera en la pantalla junto al texto desencriptado.

**Bandera:** `picoCTF{n0w_y0uv3_f1x3d_1h3m_411}`
### Notas
### Referencias