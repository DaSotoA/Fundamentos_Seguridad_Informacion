### asm1
### Descripcion
What does asm1(0x3ef) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/2495cb38ce287ca8ea254d897188445d80871d1385e00fb7fa65dd5904747b41/test.S)
### Solucion
1. Se inicializa el análisis reconociendo que el parámetro de entrada `0x3ef` se almacena en la pila en la posición `[ebp+0x8]`.
    
2. Se evalúa la primera comparación de la función en la línea `<+7>`: `cmp DWORD PTR [ebp+0x8],0x6e6`. Se compara `0x3ef` contra `0x6e6`.
    
3. En la línea `<+14>`, la instrucción `jg` (Jump if Greater) evalúa si debe saltar. Como `0x3ef` (1007 en decimal) **no es mayor** que `0x6e6` (1766 en decimal), la condición es falsa y el programa no salta, continuando a la siguiente línea.
    
4. En la línea `<+16>`, se realiza una nueva comparación: `cmp DWORD PTR [ebp+0x8],0x8`. Se compara `0x3ef` contra `0x8`.
    
5. En la línea `<+20>`, la instrucción `jne` (Jump if Not Equal) evalúa si debe saltar. Al no ser iguales (`0x3ef` != `0x8`), se cumple la condición y el flujo del programa **salta** hacia la línea `<+30>`.
    
6. En la línea `<+30>`, el valor original del parámetro se mueve al registro acumulador: `mov eax,DWORD PTR [ebp+0x8]`. El registro `eax` ahora contiene `0x3ef`.
    
7. En la línea `<+33>`, se le restan 9 unidades al registro: `sub eax,0x9`.
    
8. La resta aritmética en hexadecimal de `0x3ef - 0x9` da como resultado `0x3e6`.
    
9. En la línea `<+36>`, un salto incondicional (`jmp`) redirige el flujo al final de la función en `<+61>`, donde se recupera la base de la pila (`pop ebp`) y se ejecuta la instrucción `ret`. El valor contenido en `eax` (`0x3e6`) es el valor de retorno definitivo.
    

**Bandera:** `0x3e6`
### Notas
La lectura directa de instrucciones en Ensamblador permite predecir el comportamiento de un binario compilado. Entender la diferencia entre saltos condicionales (que dependen de los _flags_ del procesador tras un `cmp`) e incondicionales (`jmp`) es la base de la ingeniería inversa de software.
### Referencias