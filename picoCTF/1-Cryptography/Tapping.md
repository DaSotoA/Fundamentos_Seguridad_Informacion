### Tapping
### Descripcion
Theres tapping coming in from the wires.
What's it saying nc fickle-tempest.picoctf.net 49769.
### Solucion
1. Se establece conexión con el servidor proporcionado utilizando la terminal de Linux (por ejemplo, `nc fickle-tempest.picoctf.net 49769`).
    
2. El servidor responde inmediatamente con una cadena de caracteres compuesta exclusivamente por puntos (`.`), guiones (`-`) y espacios, delimitada por llaves `{ }`.
    
3. Al analizar visualmente la estructura, se identifica que el mensaje está codificado en Código Morse. Los primeros caracteres `.--. .. -.-. --- -.-. - ..-.` se traducen directamente como `PICOCTF`.
    
4. Para decodificar el resto del mensaje, se puede recurrir a una tabla de traducción manual de Código Morse, utilizar decodificadores en línea (como CyberChef o dcode.fr) o automatizar el proceso.
    
5. Si se opta por la automatización (ideal en entornos CTF), se puede desarrollar un _script_ en Python utilizando la librería `pwntools`. Este _script_ se conecta al servidor, captura la cadena, itera sobre cada bloque separado por espacios y lo compara contra un diccionario del alfabeto Morse, ignorando las llaves.
    
6. Al traducir cada bloque de puntos y rayas a su equivalente alfanumérico, se revela el texto en claro y se ensambla la bandera completa.
    

**Bandera:** `picoCTF{m0rs3c0d31sfun043a3450}`
### Notas
**Herramientas utilizadas:** Cliente de conexión de red (`nc`), decodificador de Código Morse (o _script_ en Python con `pwntools`).
### Referencias