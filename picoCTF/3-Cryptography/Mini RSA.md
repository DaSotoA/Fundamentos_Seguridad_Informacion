### Mini RSA
### Descripcion
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this:[values](https://challenge-files.picoctf.net/c_wily_courier/516811e1405ca0cb6f6a464fb3da27ea64fb10819c2e8060cf9d9c5f79612fc8/values)
### Solucion
- En la criptografía RSA estándar, la ecuación de cifrado es $C \equiv M^e \pmod N$. Esto significa matemáticamente que $M^e = C + (N \times k)$, donde $k$ es un número entero desconocido (la cantidad de veces que el número "dio la vuelta" al módulo).
    
- Si el mensaje no tuviera relleno y fuera muy pequeño ($M^e < N$), $k$ sería 0, y el mensaje original se recuperaría simplemente sacando la raíz cúbica del texto cifrado ($M = \sqrt[3]{C}$).
    
- Sin embargo, la descripción menciona que $M^e$ es "apenas un poco más grande que $N$". Esto significa que $k$ no es 0, pero es un número muy pequeño (probablemente entre 1 y 10,000).
    
- Sabiendo esto, se desarrolla un _script_ en Python que utilice un bucle para probar valores de $k$ (desde 0 hasta 10,000).
    
- Para cada iteración del bucle, el _script_ calcula $(C + N \times k)$ y luego extrae su raíz cúbica exacta utilizando librerías matemáticas de alta precisión (como `gmpy2.iroot`).
    
- Si la raíz cúbica es exacta (un número entero), se convierte ese número decimal a texto ASCII usando `long_to_bytes`.
    
- El _script_ comprueba si la cadena resultante contiene la palabra clave `picoCTF`. Si la contiene, detiene el bucle e imprime el resultado.
    
- Al ejecutar el _script_, en pocos segundos encontrará el valor correcto de $k$ (que suele ser un número de cuatro cifras) y revelará el mensaje original con la bandera.
picoCTF{e_sh0u1d_b3_lArg3r_92f4d5a5}
### Notas
**Herramientas utilizadas:** Intérprete de Python y la librería `gmpy2` (para calcular raíces cúbicas de números gigantescos de forma rápida) junto con `Crypto.Util.number` para la conversión de texto.
### Referencias