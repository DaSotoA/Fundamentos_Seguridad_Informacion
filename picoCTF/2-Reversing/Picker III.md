### Picker III
### Descripcion
Can you figure out how this program works to get the flag?
Connect to the program with netcat:`$ nc saturn.picoctf.net 57685`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/524/picker-III.py).
### Solucion
- Se examina la lógica del programa y se descubre que la opción para "actualizar la tabla" no valida a qué apuntan las nuevas variables.
    
- La estrategia consiste en secuestrar el flujo de ejecución mediante la sobrescritura de referencias.
    
- En el menú del servidor, se selecciona actualizar la tabla (Opción `3`).
    
- Se elige una función benigna existente, como `Read_variable`.
    
- Se asigna a esta función el valor de la función oculta `win`.
    
- Finalmente, se ejecuta la función modificada (Opción `2` -> `Read_variable), lo que engaña al programa para que detone el código de la bandera.


picoCTF{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_c20f5222}
### Notas
### Referencias