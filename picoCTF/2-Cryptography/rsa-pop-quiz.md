### rsa-pop-quiz
### Descripcion
Class, take your seats! It's PRIME-time for a quiz...
nc fickle-tempest.picoctf.net 56392
### Solucion
1. Se establece conexión con el servidor a través de la terminal utilizando el comando proporcionado (ej. `nc jupiter.challenges.picoctf.org 18821`).
    
2. El servidor lanza una serie de preguntas secuenciales. Para calcular las respuestas de manera eficiente antes de que la conexión expire, se recomienda desarrollar un _script_ interactivo en Python (utilizando la librería `pwntools`) o utilizar una consola de Python en paralelo.
    
3. **Pregunta 1:** Se proporcionan los números primos $p$ y $q$. Se solicita calcular el módulo $n$. Sabiendo que la fórmula base de RSA es $n = p \times q$, se multiplican ambos valores y se envía la respuesta (Factible: Y).
    
4. **Pregunta 2:** Se proporcionan $p$ y $n$. Se solicita obtener $q$. Se calcula mediante una división entera: $q = n / p$ (Factible: Y).
    
5. **Pregunta 3:** Se proporcionan la llave pública $e$ y un módulo $n$ extremadamente grande (más de 2048 bits). Se solicita calcular $p$ y $q$. Dado que la seguridad de RSA radica en la imposibilidad computacional de factorizar números primos de este tamaño con tecnología clásica, esto no es factible. (Factible: N).
    
6. **Pregunta 4:** Se proporcionan $p$ y $q$. Se pide calcular la función indicatriz de Euler (Totient), denotada como $\phi(n)$. La fórmula aplicada es $\phi(n) = (p-1) \times (q-1)$ (Factible: Y).
    
7. **Pregunta 5:** Se proporcionan un mensaje en claro (_plaintext_), $e$ y $n$. Se pide el texto cifrado. Se aplica la fórmula de cifrado RSA utilizando exponenciación modular: $c = m^e \pmod n$ (Factible: Y).
    
8. **Pregunta 6:** Se proporcionan un texto cifrado, $e$ y un $n$ grande. Se pide el texto en claro. Sin conocer $p$ y $q$ (y por tanto, sin $\phi(n)$ y $d$), es computacionalmente inviable descifrar el mensaje (Factible: N).
    
9. **Pregunta 7:** Se proporcionan $p$, $q$ y $e$. Se pide calcular la llave privada $d$. Primero se calcula $\phi(n) = (p-1) \times (q-1)$, y luego se calcula $d$ como el inverso modular de $e$ módulo $\phi(n)$ usando librerías matemáticas como `sympy.mod_inverse` (Factible: Y).
    
10. **Pregunta 8:** Se proporcionan el texto cifrado, $p$, $e$ y $n$. Se solicita descifrar y obtener el texto en plano original. Dado que se tiene $p$, se puede derivar $q = n / p$. Con ambos primos, se calcula $\phi(n)$, luego la llave privada $d$, y finalmente se aplica la fórmula de descifrado $m = c^d \pmod n$.
    
11. Tras enviar el gran número decimal resultante de la última pregunta, el servidor lo valida. Ese número decimal se debe convertir a formato Hexadecimal y, posteriormente, decodificar de Hexadecimal a caracteres ASCII legibles, revelando así la bandera.
    

**Bandera:** `picoCTF{wA8_th4till3aGal..o288ce54c}`
### Notas
**Herramientas utilizadas:** Intérprete de Python, librería `pwntools` para automatización de respuestas en el servidor de red, y `sympy` para operaciones matemáticas complejas (como el inverso modular).
### Referencias