### basic-mod1
### Descripcion
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
### Solucion
1. Se descarga y analiza el archivo `message.txt` proporcionado por el reto, identificando la lista de enteros grandes.
    
2. Comprendiendo la lógica planteada, se hace evidente que es una variante sencilla de un cifrado de sustitución basado en aritmética modular, por lo que el proceso se puede automatizar fácilmente.
    
3. Se desarrolla un _script_ en Python para procesar la lista. El programa realiza lo siguiente:
    
    - Lee el contenido del archivo y separa los números en un arreglo.
        
    - Itera sobre cada número, aplicando la operación `numero % 37` para obtener el residuo.
        
    - Utiliza constantes como `string.ascii_uppercase` y `string.digits` nativas de Python para mapear el residuo obtenido al carácter correspondiente según las reglas del reto.
        
4. Al ejecutar la operación módulo sobre la serie de números, se obtiene una lista de residuos exactos.
    
5. Aplicando el diccionario de sustitución a esos residuos, los valores se traducen directamente a los caracteres alfanuméricos en claro (por ejemplo, 17 se convierte en R, 26 en 0, 20 en U, 13 en N, y 3 en D).
    
6. La decodificación final revela la cadena de texto exacta asignada a la instancia del reto.
    
7. Finalmente, se envuelve la cadena obtenida en el formato estándar de la plataforma para su envío.
    

**Bandera:** `picoCTF{R0UND_N_R0UND_ADD17EC2}`
### Notas
**Herramientas utilizadas:** Intérprete de Python para lectura automatizada de archivos y operaciones aritméticas.
### Referencias