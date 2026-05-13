### asm3
### Descripcion
What does asm3(0xdaba8a6c,0xfa8a55d0,0xd7771dae) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/260b193c4ea89ef080c7a828081e482f06628204337fc389755d5de67bd30dcd/test.S)
### Solucion
1. Al pasar los parámetros `asm3(0xdaba8a6c, 0xfa8a55d0, 0xd7771dae)`, estos se apilan utilizando el formato _Little Endian_ (el _byte_ menos significativo va en la dirección de memoria más baja). El mapa de memoria relevante queda así:
    
    - **Parámetro 1:** `[ebp+0x8] = 0x6c`, `[ebp+0x9] = 0x8a`, `[ebp+0xa] = 0xba`, `[ebp+0xb] = 0xda`
        
    - **Parámetro 2:** `[ebp+0xc] = 0xd0`, `[ebp+0xd] = 0x55`, `[ebp+0xe] = 0x8a`, `[ebp+0xf] = 0xfa`
        
    - **Parámetro 3:** `[ebp+0x10] = 0xae`, `[ebp+0x11] = 0x1d`, `[ebp+0x12] = 0x77`, `[ebp+0x13] = 0xd7`
        
2. `<+7>: xor eax, eax` -> Limpia completamente el registro acumulador. `eax = 0x00000000`.
    
3. `<+9>: mov ah, BYTE PTR [ebp+0x9]` -> Mueve el _byte_ `0x8a` a la parte alta del registro de 16 bits (`ah`). Por lo tanto, `ax = 0x8a00`.
    
4. `<+12>: shl ax, 0x10` -> _Instrucción trampa._ Desplaza el registro `ax` (que mide 16 bits) 16 posiciones a la izquierda. Al empujar todos los bits fuera de su límite, el registro se vacía por completo. `ax = 0x0000`.
    
5. `<+16>: sub al, BYTE PTR [ebp+0xd]` -> Resta `0x55` al registro `al` (que vale `0x00`). Ocurre un desbordamiento inferior (_underflow_): `0x00 - 0x55 = 0xab`. Ahora, `ax = 0x00ab`.
    
6. `<+19>: add ah, BYTE PTR [ebp+0xf]` -> Suma `0xfa` al registro `ah` (que vale `0x00`). Ahora, `ax = 0xfaab`.
    
7. `<+22>: xor ax, WORD PTR [ebp+0x10]` -> Aplica un XOR entre `ax` (`0xfaab`) y el _Word_ (16 bits) ubicado en `[ebp+0x10]`. Por la regla _Little Endian_, los _bytes_ `ae` y `1d` se leen invertidos como `0x1dae`.
    
8. Se ejecuta la operación XOR final: `0xfaab ^ 0x1dae`.
    
    - En binario: `1111101010101011` ^ `0001110110101110` = `1110011100000101`.
        
    - El resultado en hexadecimal es `0xe705`.
        
9. El bloque termina y retorna el valor contenido en `eax` (cuyos 16 bits superiores nunca se modificaron).
    

**Bandera:** `0xe705`
### Notas
El registro acumulador de 32 bits (`eax`) se subdivide en la mitad inferior de 16 bits (`ax`), la cual a su vez se divide en la parte alta (`ah`) y la parte baja (`al`) de 8 bits cada una. Comprender estas subdivisiones es vital, ya que las operaciones aplicadas directamente a `al` o `ah` no alteran los demás bits de `eax`.
### Referencias