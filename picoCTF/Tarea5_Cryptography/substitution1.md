### substitution1
### Descripcion
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.
Download the message [here](https://artifacts.picoctf.net/c/182/message.txt).
### Solucion
- Se descarga y visualiza el archivo `message.txt` proporcionado por el reto.
    
- Al analizar el contenido, se observa un bloque de texto incomprensible que, sin embargo, conserva intactos los espacios, la longitud de las palabras, las comillas y los signos de puntuación. Esta estructura es la firma principal de un cifrado de sustitución simple.
    
- Al carecer de la llave, se debe explotar la principal debilidad de este cifrado: las letras en cualquier idioma no se utilizan con la misma frecuencia. En inglés, por ejemplo, la letra "E" es la más común, seguida de la "T", "A", "O", etc.
    
- En lugar de contar las letras manualmente y adivinar palabras comunes (como "THE" o "AND"), se recurre a una herramienta OSINT especializada en criptoanálisis estadístico: **quipqiup**.
    
- Se copia la totalidad del texto cifrado y se pega en la interfaz web de quipqiup.
    
- El algoritmo de la herramienta compara las frecuencias de las letras del texto con diccionarios masivos del idioma inglés y resuelve el rompecabezas en milisegundos, arrojando el texto plano.
    
- Al leer el texto descifrado, se localiza la bandera en el último párrafo, envuelta en el formato clásico.


`picoCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}`
### Notas
**Herramientas utilizadas:** Solucionador automatizado de criptogramas web ([quipqiup.com](https://quipqiup.com/)).
### Referencias