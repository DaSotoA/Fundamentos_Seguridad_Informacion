### substitution2
### Descripcion
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher?
Download the message [here](https://artifacts.picoctf.net/c/112/message.txt).
### Solucion
- Se descarga y examina el archivo `message.txt` dentro del entorno de trabajo.
    
- Se confirma visualmente que la estructura del texto (espacios, saltos de línea, puntuación) se mantiene intacta, indicando un cifrado de sustitución simple.
    
- Se recurre nuevamente a la herramienta de criptoanálisis OSINT **quipqiup** para realizar un Análisis de Frecuencias automatizado.
    
- Se copia todo el texto cifrado y se pega en el decodificador.
    
- _Paso Crítico:_ A diferencia del nivel anterior, si la herramienta automática tiene problemas deduciendo palabras poco comunes, se procede a inyectar conocimiento previo. Al observar el texto cifrado, se identifica la palabra que representa la bandera por su formato (ej. `xyzqABC{...}`).
    
- Sabiendo con absoluta certeza que esa cadena debe significar `picoCTF{`, se le proporciona esta pista exacta a la herramienta de descifrado para forzar el mapeo de esas 7 letras.
    
- Con esta restricción aplicada, el algoritmo recalcula las probabilidades y descifra el texto completo con precisión del 100%.
    
- Se ubica el último párrafo del texto traducido para extraer la bandera.

picoCTF{N6R4M_4N41Y515_15_73D10U5_8E1BF808}
### Notas
### Referencias
