### Easy1
### Descripcion
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this?We've given you the encrypted flag, key, and a table to help UFJKXQZQUNB with the key of SOLVECRYPTO. Can you use this [table](https://challenge-files.picoctf.net/c_fickle_tempest/859ffc313a4d8b63149f144745043a7312fc4f993e405eeeb8ee5ae6ca8444a8/table.txt) to solve it?.
### Solucion
1. Se analizan los datos proporcionados. El archivo `table.txt` contiene una matriz alfabética estándar de 26x26 que ilustra cómo se realiza la suma modular entre las letras del abecedario.
    
2. El proceso de cifrado funciona emparejando cada carácter del texto original con un carácter de la llave para generar la letra cifrada. Para descifrarlo manualmente, se realiza el proceso inverso utilizando la tabla proporcionada.
    
3. Se toma la primera letra de la llave (`S`) y se busca en el eje vertical de la tabla. Luego, se recorre esa fila hacia la derecha hasta encontrar la primera letra del texto cifrado (`U`). Al subir en línea recta desde esa `U` hasta el eje horizontal superior, se revela la primera letra original: `C`.
    
4. Se repite este procedimiento con el resto de los caracteres (por ejemplo, la letra `O` de la llave contra la `F` del cifrado revela la `R`).
    
5. Alternativamente, este proceso de "resta modular" puede ser automatizado en la terminal escribiendo un pequeño _script_ (por ejemplo, en Python). A nivel lógico, se restan los valores numéricos ASCII de la llave a los valores del texto cifrado, aplicando un envoltorio de módulo 26 para reiniciar el ciclo en caso de que el valor sobrepase la 'A' o la 'Z'.
    
6. Al completar la decodificación de toda la cadena, el texto en plano revelado es `CRYPTOISFUN`.
    
7. Se envuelve la cadena descubierta en el formato estándar de la plataforma para validar el desafío.
    

**Bandera:** `picoCTF{CRYPTOISFUN}`
### Notas
**Herramientas utilizadas:** Análisis manual visual (usando la _Tabula Recta_) o un _script_ automatizado en Python para aplicar aritmética modular.
### Referencias
