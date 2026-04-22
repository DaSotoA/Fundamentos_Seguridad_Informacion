### caesar
### Descripcion
Decrypt this message.Message: [message](https://challenge-files.picoctf.net/c_fickle_tempest/bfd7c036228a50ff9e76dfc29ac6cec116f209f0db26506497997f0aca083105/data.enc)
### Solucion
1. Se descarga el archivo `ciphertext` proporcionado en las instrucciones del reto y se inspecciona su contenido, revelando una cadena de caracteres ininteligible.
    
2. Dado que el Cifrado César funciona desplazando cada letra un número fijo de posiciones en el alfabeto, y al carecer de la clave numérica, la táctica más eficiente es probar todas las combinaciones posibles.
    
3. Se implementa un ataque de fuerza bruta. Esto puede realizarse desarrollando un _script_ sencillo en Python que itere del 0 al 25, aplicando la operación inversa del cifrado a la cadena original y mostrando cada resultado en pantalla. Alternativamente, se pueden emplear decodificadores en línea (como CyberChef o dcode.fr).
    
4. Al generar las 26 combinaciones posibles, el participante debe inspeccionar visualmente la lista de salidas en la terminal.
    
5. De todas las rotaciones, solo una arroja un texto con un sentido semántico lógico y legible (en el caso del artículo, la cadena que inicia con `crossingtherubicon...`).
    
6. Se extrae esta cadena de texto en claro y se envuelve dentro del formato estándar de la plataforma para formar la respuesta final.
    

**Bandera:** picoCTF{crossingtherubicongzsvuhaf}
### Notas
**Herramientas utilizadas:** _Script_ de Python para iteración o herramientas gráficas de decodificación ROT.
### Referencias
