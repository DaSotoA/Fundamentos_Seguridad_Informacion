### vault-door-4
### Descripcion
This vault uses ASCII encoding for the password.
The source code for this vault is here: [VaultDoor4.java](https://challenge-files.picoctf.net/c_fickle_tempest/92aa3358fb5bde2c6f38b39fbf2d59af8c44220bc0662ce636d655f0ad3a1a8d/VaultDoor4.java)
### Solucion
1. Se analiza el código fuente `VaultDoor4.java` generado por la plataforma.
    
2. Se localiza la función `checkPassword()` y se extrae el arreglo `myBytes`, el cual contiene 32 valores divididos en cuatro bloques de 8 _bytes_:
    
    - **Índices 0 al 7:** Valores en base Decimal (ej. `106`).
        
    - **Índices 8 al 15:** Valores en base Hexadecimal (ej. `0x55`).
        
    - **Índices 16 al 23:** Valores en base Octal (ej. `0142`).
        
    - **Índices 24 al 31:** Caracteres ASCII literales (ej. `'e'`, `'9'`, `'4'`, etc.).
        
3. Para desofuscar la cadena, se convierte cada valor numérico a su carácter ASCII correspondiente.
    
4. Se desarrolla un _script_ en Python que declara los enteros en sus respectivas bases (`0x` para hexadecimal y `0o` para octal) y los transforma directamente a texto utilizando la función `chr()`.
    
5. Al procesar el arreglo exacto de la instancia, los distintos bloques se traducen como `jU5t_4_b`, `UnCh_0f_`, `bYt3s_b4` y `e943c3a0`, revelando la contraseña completa.
    

**Bandera:** `picoCTF{jU5t_4_bUnCh_0f_bYt3s_b4e943c3a0}`
### Notas
### Referencias