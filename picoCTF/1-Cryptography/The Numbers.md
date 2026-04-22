### The Numbers
### Descripcion
The numbers... what do they mean?[numbers.png](https://challenge-files.picoctf.net/c_fickle_tempest/7b39deba4212c233b1628c93f16639ed02ad90f51436d2a8914bb11f74a982d3/the_numbers.png)
### Solucion
1. Se descarga y visualiza el archivo de imagen proporcionado en las instrucciones del reto.
    
2. Al inspeccionar visualmente la secuencia de números, se observa que la estructura y el uso de llaves coinciden con el formato estándar de las banderas de la plataforma (una palabra inicial seguida de contenido entre llaves).
    
3. Analizando el primer bloque de números (que típicamente correspondería a la palabra `PICOCTF`), se nota que los valores oscilan únicamente entre el 1 y el 26.
    
4. Se realiza una prueba de correspondencia directa con el abecedario inglés, donde a cada número se le asigna su posición alfabética (1=A, 2=B, 3=C... 16=P, 9=I, etc.). Al hacer esto, la secuencia inicial se traduce exactamente como "PICOCTF", confirmando el método de cifrado.
    
5. Con el patrón descubierto, se procede a convertir el resto de los números ubicados dentro de las llaves por sus respectivas letras. Esta conversión puede realizarse de forma manual utilizando una tabla de referencia alfabética, o de forma automatizada escribiendo un breve _script_ en lenguajes como Python.
    
6. Al finalizar el mapeo de toda la secuencia numérica, el texto oculto se revela en su totalidad.
    

**Bandera:** `PICOCTF{THENUMBERSMASON}`
### Notas
**Herramientas utilizadas:** Visor de imágenes y tabla de conversión alfabética (o _script_ de Python).
### Referencias