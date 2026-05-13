### asm2
### Descripcion
What does asm2(0xa,0x15) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/1b461fce4f77f2756ffeade3af119ec77d49db6fd9831387af61f9e3dec7a839/test.S)
### Solucion
1. Se identifican los parámetros de entrada en la pila: el primer argumento es `0xa` (almacenado en `[ebp+0x8]`) y el segundo es `0x15` (almacenado en `[ebp+0xc]`).
    
2. En la línea `<+7>`, la instrucción `sub esp,0x10` reserva 16 _bytes_ en la pila para variables locales.
    
3. Se inicializan dos variables locales:
    
    - **Variable 1** en `[ebp-0x4]` recibe el valor del segundo parámetro: `0x15` (21 en decimal).
        
    - **Variable 2** en `[ebp-0x8]` recibe el valor del primer parámetro: `0xa` (10 en decimal).
        
4. El programa hace un salto incondicional en `<+22>` hacia la línea `<+32>`, que actúa como la evaluación de un bucle `while`.
    
5. En `<+32>`, se compara la Variable 2 con el valor `0x84ab` (33963 en decimal). La línea `<+39>` usa `jle` (Jump if Less or Equal), lo que significa que el bucle continuará mientras `Variable 2 <= 0x84ab`.
    
6. Dentro del bucle (líneas `<+24>` y `<+28>`):
    
    - A la Variable 1 se le suma `0x1` por cada iteración.
        
    - A la Variable 2 se le suma `0x37` (55 en decimal) por cada iteración.
        
7. Para evitar simular esto a mano paso a paso, se traduce a una ecuación:
    
    - La Variable 2 debe crecer desde 10 hasta superar 33963, en pasos de 55.
        
    - Diferencia: $33963 - 10 = 33953$.
        
    - Division: $33953 / 55 \approx 617.32$.
        
    - Dado que la condición permite ser "menor o igual", el ciclo da una vuelta extra, ejecutándose exactamente **618 veces**.
        
8. Se calcula el valor final de la Variable 1: inicia en 21 y se le suma 1 por cada una de las 618 vueltas.
    
    - $21 + 618 = 639$.
        
9. En la línea `<+41>`, la Variable 1 se mueve a `eax` para ser el valor de retorno. Al convertir 639 a formato hexadecimal, obtenemos `0x27f`.
    

**Bandera:** `0x27f`
### Notas
Este reto demuestra cómo los compiladores de C traducen un ciclo `while` o `for`. Primero configuran los contadores en la pila (usando `ebp` con desplazamientos negativos), luego hacen un salto hacia la comprobación de la condición, y si se cumple, regresan al cuerpo del bucle para aplicar los incrementos.
### Referencias