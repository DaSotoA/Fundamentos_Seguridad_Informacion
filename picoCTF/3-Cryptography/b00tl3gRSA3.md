### b00tl3gRSA3
### Descripcion
Why use p and q when I can use more?Connect with nc fickle-tempest.picoctf.net 64663.
### Solucion
- Se examinan los valores proporcionados. Al tener un exponente público estándar ($e = 65537$), ataques como el de Wiener (utilizado en `b00tl3gRSA2`) quedan descartados.
    
- Se sospecha que el módulo $n$ es vulnerable a una factorización rápida debido a una mala generación de primos. Sin embargo, al intentar enviar $n$ a la base de datos de FactorDB, el número no se encuentra completamente factorizado.
    
- Al intentar ataques locales de fuerza bruta matemáticos rápidos (como la _Factorización de Fermat_ o el algoritmo _p-1 de Pollard_) mediante _scripts_ en Python dentro de la webshell de picoCTF, el proceso falla o requiere un poder de cómputo inasumible, revelando que los factores son múltiples y complejos.
    
- Para evitar instalar herramientas pesadas como _YAFU_ en un entorno local, se recurre a calculadoras criptográficas distribuidas especializadas (como la calculadora ECM de Alpertron) para aplicar algoritmos avanzados (Criba Cuadrática, Curvas Elípticas, etc.) de manera eficiente.
    
- Se introduce el valor de $n$ en la calculadora. Tras varios minutos de procesamiento, la herramienta logra romper la seguridad y revela que $n$ no estaba compuesto por 2 primos, sino que había sido fracturado deliberadamente en **34 números primos distintos** (desde `8694873457` hasta `16406056253`).
    
- Con los 34 factores descubiertos, se diseña un _script_ en Python para reconstruir la llave privada ($d$). En lugar de la fórmula tradicional $\phi(n) = (p-1)(q-1)$, la función Totient de Euler debe iterar sobre todos los factores multiplicando $(f_i - 1)$ por cada primo descubierto.
    
- Una vez obtenido el nuevo $\phi(n)$, se calcula el inverso modular $d = e^{-1} \pmod{\phi(n)}$.
    
- Se aplica la fórmula de descifrado $m = c^d \pmod n$.
    
- El resultado numérico es convertido a su equivalente en hexadecimal y posteriormente decodificado a bytes (texto ASCII). El resultado incluye caracteres basura (ruido o _padding_), por lo que el _script_ filtra la salida para aislar únicamente la cadena que comienza con `picoCTF`.

picoCTF{too_many_fact0rs_3023548}
### Notas
**Herramientas utilizadas:** Calculadora criptográfica externa (Alpertron ECM) para Criba Cuadrática y un _script_ en Python para automatizar el descifrado de Multi-Prime RSA e ignorar el ruido de codificación.
### Referencias
