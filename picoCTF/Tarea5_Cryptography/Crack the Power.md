### Crack the Power
### Descripcion
We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag.
Download the [message](https://challenge-files.picoctf.net/c_amiable_citadel/fddf51f15bd9f4145c4a4ebee5dfe7994bdab6393453f41f02c59cfd23a87fda/message.txt).
### Solucion
1. Se descargan y analizan los parámetros criptográficos proporcionados en el archivo del reto.
    
2. Al examinar los valores, se identifica una anomalía crítica en el exponente público $e$. A diferencia del estándar seguro (habitualmente 65537), el exponente utilizado es extremadamente pequeño ($e = 20$).
    
3. Esto expone el cifrado a lo que se conoce como un "Ataque de Exponente Público Pequeño" (_Low Public Exponent Attack_), una variante de los ataques descritos por Coppersmith.
    
4. La vulnerabilidad matemática radica en la ausencia de relleno (_padding_) y en el tamaño del mensaje. Si el mensaje en claro elevado al exponente es menor que el módulo ($m^e < N$), la operación de módulo ($\pmod N$) nunca "envuelve" el número.
    
5. Por lo tanto, la ecuación $c \equiv m^e \pmod N$ se degrada a una simple potenciación aritmética: $c = m^e$.
    
6. Para recuperar el mensaje original ($m$), ya no es necesario utilizar la llave privada ($d$); basta con extraer la raíz número 20 del texto cifrado ($m = \sqrt[20]{c}$).
    
7. Dado que los números son demasiado grandes para las funciones matemáticas de punto flotante tradicionales, se diseña un _script_ en Python que utiliza una búsqueda binaria para calcular la raíz entera exacta de forma rápida.
    
8. Una vez obtenida la raíz entera ($m$), el resultado se convierte desde su formato numérico a _bytes_ para revelar el texto legible en ASCII.
    

**Bandera:** `picoCTF{t1ny_e_f053d79c}`
### Notas

### Referencias
