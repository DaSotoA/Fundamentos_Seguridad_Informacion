### Vigenere
### Descripcion
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".
### Solucion
- Se descarga y examina el archivo `cipher.txt`. En su interior, se observa una cadena de texto (ej. `rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_...}`) que mantiene la estructura y símbolos del formato de bandera `picoCTF{}`, lo que indica que los números y caracteres especiales no fueron alterados por el cifrado.
    
- A diferencia del Cifrado César (que desplaza todas las letras la misma cantidad de posiciones), el Cifrado de Vigenère es polialfabético. Utiliza la llave `CYLAB` repitiéndola cíclicamente sobre el mensaje (`CYLABCYLABCYL...`) para determinar un desplazamiento distinto para cada letra.
    
- Existen múltiples formas de descifrarlo:
    
    - **Enfoque OSINT:** Se puede copiar el texto cifrado y pegarlo en una herramienta en línea como _CyberChef_ (módulo "Vigenère Decode") o el decodificador de _dCode.fr_, introduciendo `CYLAB` como la llave.
        
    - **Enfoque Programático:** Se desarrolla un _script_ en Python que itera sobre cada letra del texto cifrado, calcula el desplazamiento inverso según la letra de la llave correspondiente (ej. 'C' = desplazar -2 posiciones, 'Y' = -24 posiciones) y respeta las mayúsculas, minúsculas, números y símbolos.
        
- Al aplicar la decodificación, la palabra `rgnoDVD` se traduce perfectamente como `picoCTF`, y el resto del mensaje recupera su sentido legible.

**`picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}`**
### Notas

### Referencias