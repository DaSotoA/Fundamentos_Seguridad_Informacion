### EVEN RSA CAN BE BROKEN???
### Descripcion
This service provides you an encrypted flag. Can you decrypt it with just N & e?Connect to the program with netcat:
`$ nc verbal-sleep.picoctf.net 54757`
The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/1ce03df0245f787fd1d116ac8502051905222e1138057a4070872f3a5d38c232/encrypt.py).
### Solucion
1. Se establece conexión con el servicio a través de la terminal, lo que arroja los parámetros matemáticos $N$, $e$ y el texto cifrado ($c$).
    
2. Al examinar minuciosamente el valor del módulo $N$, resalta un detalle crítico que compromete todo el sistema: termina en un dígito par, lo que significa que el número completo es divisible entre 2.
    
3. Matemáticamente, el módulo $N$ en RSA se genera multiplicando dos números primos ($N = p \times q$). Dado que el único número primo par existente es el 2, se deduce de manera absoluta que uno de los primos generadores (por ejemplo, $p$) tiene el valor exacto de 2.
    
4. Con esta revelación, la factorización de $N$ se vuelve una operación trivial. Se divide $N$ entre 2 para descubrir el segundo factor primo ($q = N / 2$).
    
5. Una vez obtenidos $p=2$ y $q$, se calcula la función Totient de Euler: $\phi(n) = (p-1)(q-1)$. Dado que $p-1 = 1$, la fórmula se simplifica drásticamente a $\phi(n) = q-1$.
    
6. Con el valor de $\phi(n)$ al descubierto, se procede a calcular la llave privada $d$, correspondiente al inverso modular de $e \pmod{\phi(n)}$.
    
7. Teniendo el exponente privado $d$, se ejecuta la fórmula estándar de descifrado RSA: $m = c^d \pmod N$.
    
8. El resultado es un entero gigantesco ($m$) que finalmente se decodifica desde su formato de _bytes_ a texto legible en ASCII, revelando el mensaje oculto.
    

**Bandera:** picoCTF{tw0_1$_pr!m375129bb1}
### Notas

### Referencias