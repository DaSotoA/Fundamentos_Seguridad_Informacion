### b00tl3gRSA2
### Descripcion
In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e?
Connect with nc fickle-tempest.picoctf.net 62333.
### Solucion
1. Se analizan los valores proporcionados por el reto. Se observa que el exponente público $e$ es un número gigantesco, casi del mismo tamaño que el módulo $n$. En una implementación segura de RSA, $e$ suele ser un número primo pequeño (como 65537).
    
2. Se deduce matemáticamente que, si $e$ es enorme, el exponente privado $d$ tuvo que haber sido elegido con un valor numérico muy pequeño para que la ecuación $(e \times d) \pmod{\phi(n)} = 1$ funcionara.
    
3. Un valor $d$ excesivamente pequeño (específicamente cuando $d < \frac{1}{3} n^{1/4}$) hace que el sistema sea vulnerable al **Ataque de Wiener**. Este ataque no intenta factorizar el módulo $n$ por fuerza bruta, sino que utiliza fracciones continuas para aproximar la relación matemática entre $e$ y $n$.
    
4. Para ejecutar el ataque, se implementa un _script_ en Python que calcula el desarrollo en fracción continua de $e/n$.
    
5. A partir de esa fracción continua, el algoritmo genera una serie de fracciones aproximadas (llamadas "convergentes"). Cada convergente se prueba matemáticamente como un candidato potencial para simular la fracción $k/d$.
    
6. El _script_ itera sobre estos candidatos hasta encontrar un $d$ que logre resolver correctamente la ecuación cuadrática subyacente para aislar los factores $p$ y $q$.
    
7. Una vez que el algoritmo de Wiener recupera exitosamente la llave privada $d$, se aplica la fórmula estándar de descifrado de RSA: $m = c^d \pmod n$.
    
8. El resultado es un número entero extenso que, al convertirse a formato de bytes (texto ASCII), revela la cadena oculta.
    

**Bandera:** `picoCTF{bad_1d3a5_3801255}`
### Notas
**Herramientas utilizadas:** Intérprete de Python y un _script_ automatizado del Ataque de Wiener (haciendo uso de librerías nativas como `math.isqrt` para calcular raíces cuadradas exactas y validación de ecuaciones de segundo grado).
### Referencias
