### substitution0
### Descripcion
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?Download the message [here](https://artifacts.picoctf.net/c/154/message.txt).
### Solucion
- Se descarga y visualiza el archivo `message.txt` dentro del entorno de trabajo.
    
- Al leer el contenido, se identifica una cadena de 26 letras únicas en mayúsculas en la primera línea. Esta cadena funciona como la llave de descifrado, indicando cómo el alfabeto estándar (`A-Z`) ha sido reemplazado.
    
- El resto del documento contiene un texto que carece de sentido pero conserva la estructura de párrafos, longitud de palabras y signos de puntuación normales. Este es el sello distintivo de un cifrado de sustitución simple.
    
- Para descifrar el mensaje, se debe mapear cada letra del texto ofuscado a su posición correspondiente en el alfabeto estándar, utilizando la llave de la primera línea como diccionario inverso.
    
- Se diseña un _script_ para automatizar el mapeo de caracteres, asegurando que se respete el uso de mayúsculas y minúsculas originales.
    
- Al ejecutar la traducción sobre todo el bloque de texto, el documento recupera su legibilidad original y revela la bandera en la última línea.

`picoCTF{5UB5717U710N_3V0LU710N_357BF9FF}`
### Notas
**Herramientas utilizadas:** Intérprete de Python con la función nativa `maketrans` para reemplazo de caracteres.
### Referencias