### rail-fence
### Descripcion
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?
Download the message [here](https://artifacts.picoctf.net/c/188/message.txt).
Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.
### Solucion
- Se descarga y visualiza el archivo de texto que contiene el mensaje ofuscado (el cual suele lucir como una mezcla de letras, números y guiones bajos desordenados).
    
- Sabiendo que es un cifrado Rail Fence, la forma más rápida y efectiva de resolverlo sin programar el algoritmo desde cero es utilizar una herramienta de análisis criptográfico OSINT, como [CyberChef](https://gchq.github.io/CyberChef/) o cualquier decodificador web específico de "Rail Fence Cipher".
    
- En la herramienta, se selecciona la operación de descifrado (_Decrypt_) y se configura el parámetro de la llave (número de rieles o _height_) exactamente en **4**.
    
- Se pega el texto cifrado en la caja de entrada. Es **crítico** asegurarse de no copiar ni un solo espacio en blanco adicional al inicio o al final del texto; de lo contrario, la matriz de posiciones se desfasará y el texto descifrado será ilegible.
    
- Al aplicar la operación con 4 rieles, la herramienta reconstruye el texto plano (que se leerá como algo similar a `WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_...`).
    
- Finalmente, se toma ese texto descifrado y se envuelve manualmente en el formato estándar de la plataforma.

**`picoCTF{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_4A76B997}`**
### Notas
**Herramientas utilizadas:** Utilidades web de decodificación (CyberChef)
### Referencias