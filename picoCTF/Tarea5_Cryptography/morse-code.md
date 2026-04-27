### morse-code
### Descripcion
Morse code is well known. Can you decrypt this?
Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).
Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.
### Solucion
1. Se descarga el archivo de audio proporcionado por el reto.
    
2. Al reproducir el archivo, se escucha claramente una serie de pitidos cortos y largos, lo que confirma que el mensaje está codificado en Código Morse (donde los pitidos cortos representan "puntos" y los largos representan "rayas").
    
3. Existen dos enfoques principales para decodificar el mensaje:
    
    - **Enfoque manual/visual (Recomendado por el reto):** Se utiliza un software de edición de audio como `Audacity`. Al abrir el archivo en el programa, se puede observar la forma de onda (_waveform_) o el espectrograma, lo que permite "ver" literalmente los puntos y rayas y traducirlos letra por letra usando una tabla estándar de Código Morse.
        
    - **Enfoque automatizado (OSINT):** Se utiliza una herramienta en línea especializada en procesamiento de señales, como el _Morse Code Audio Decoder_. Se sube el archivo de audio directamente a la página y el algoritmo extrae el texto plano analizando las frecuencias de los tonos.
        
4. Una vez obtenida la cadena de texto decodificada: `WH47 H47H 90D W20U9H7`.
    
5. Se aplican las reglas de formateo descritas en la pista del reto: envolver el mensaje con `picoCTF{}`, reemplazar los espacios (pausas) con guiones bajos (`_`) y convertir todas las letras a minúsculas.
    

**Bandera:** `picoCTF{wh47_h47h_90d_w20u9h7}`
### Notas
**Herramientas utilizadas:** Software de análisis de audio local (`Audacity`) o herramientas web de reconocimiento acústico (como Morse Code Audio Decoder).
### Referencias