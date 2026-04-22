### interencdec
### Descripcion
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/111/enc_flag).
### Solucion
- Se descarga el archivo de texto y se examina su contenido. En su interior se encuentra la siguiente cadena: `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg==`.
    
- Por la distribución de los caracteres (letras mayúsculas, minúsculas, números) y el relleno con signos de igual (`=`) al final, se identifica inmediatamente que el texto está codificado bajo el esquema Base64.
    
- Se procede a realizar la primera decodificación Base64 en la terminal o utilizando herramientas como CyberChef. El resultado devuelto será un texto envuelto en la sintaxis `b'...'`, la cual es la representación estándar de un formato de _byte-string_ en el lenguaje Python.
    
- Se debe "limpiar" esta cadena, eliminando manualmente los delimitadores `b'` al inicio y `'` al final. Lo que queda en medio resulta ser otra cadena válida en formato Base64.
    
- Se realiza una segunda decodificación Base64 a esta nueva cadena limpia. El resultado muestra una estructura muy similar a la de una bandera (por ejemplo, `wpjvJAM{...}`), pero las letras no coinciden con la palabra `picoCTF`, indicando que se ha aplicado un algoritmo de cifrado adicional.
    
- Sabiendo que la estructura se mantiene pero las letras están desplazadas, se deduce que se utilizó un clásico Cifrado César (cifrado por sustitución).
    
- Se introduce el texto en un decodificador de Cifrado César para iterar por todas las rotaciones posibles (fuerza bruta). Al llegar a un desplazamiento de `-7` posiciones (equivalente a un desplazamiento de `+19`), el texto se vuelve legible y revela la respuesta correcta.

picoCTF{caesar_d3cr9pt3d_890d2379}
### Notas
**Herramientas utilizadas:** Decodificador Base64 (ej. comando `base64 -d` en Linux) y decodificador de Cifrado César (plataformas como CyberChef, Cryptii o dcode.fr).
### Referencias
- https://cryptii.com/pipes/caesar-cipher/
- https://cyberchef.io/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true)&input=ZDNCcWRrcEJUWHRxYUd4NmFIbGZhek5xZVRsM1lUTnJYemc1TUdzeU16YzVmUT09Cg

