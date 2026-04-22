### Flags
### Descripcion
What do the [flags](https://challenge-files.picoctf.net/c_fickle_tempest/214c9d918be75903d4183c35fa4b94ef60dba05fc4df37c97cf0868087067372/flag.png) mean?
### Solucion
1. Se descarga y analiza el archivo de imagen proporcionado por el reto. Se observa que contiene una serie de banderas que actúan como caracteres individuales, delimitadas por el formato clásico de las llaves `{ }`.
    
2. Para identificar el tipo de código visual, se puede aislar una de las banderas y realizar una Búsqueda Inversa de Imágenes (por ejemplo, utilizando Google Lens o Google Image Search).
    
3. La búsqueda revela que los símbolos corresponden al **Código Internacional de Señales Marítimas** (International Maritime Signal Flags), un sistema estándar utilizado por los barcos para comunicarse visualmente a distancia.
    
4. Se consulta una tabla de referencia del alfabeto de banderas marítimas internacionales (disponible en fuentes como Wikipedia).
    
5. Se procede a traducir visualmente cada bandera de la imagen comparándola con el alfabeto marítimo.
    
6. La primera secuencia de banderas antes de la llave traduce directamente la palabra `PICOCTF`.
    
7. Continuando con la traducción de las banderas dentro de las llaves, considerando que el sistema también incluye representaciones para números enteros, se extrae el texto en claro.
    

**Bandera:** `PICOCTF{F1AG5AND5TUFF}`
### Notas
**Herramientas utilizadas:** Búsqueda Inversa de Imágenes y tabla de referencia del Código Internacional de Señales Marítimas.
### Referencias