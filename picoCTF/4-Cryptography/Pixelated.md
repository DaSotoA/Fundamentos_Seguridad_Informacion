### Pixelated
### Descripcion
I have these 2 images, can you make a flag out of them?[scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/2180f74b7f56abc330252d0146f6a044f8e35027142e5cb16c9160c37a0c630f/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/2180f74b7f56abc330252d0146f6a044f8e35027142e5cb16c9160c37a0c630f/scrambled2.png)
### Solucion
1. Se descargan y analizan ambas imágenes dentro del entorno de trabajo. Al observar que poseen exactamente las mismas dimensiones, se infiere que las coordenadas de los píxeles de una imagen están emparejadas criptográficamente con las coordenadas homólogas de la otra.
    
2. El concepto subyacente es la "Criptografía Visual", un método de compartición de secretos donde un dato se divide en múltiples capas (o "sombras"). Ninguna capa individual revela información por sí sola, pero al superponerlas correctamente, la imagen original se materializa.
    
3. Para revelar el mensaje oculto operando directamente desde un entorno de terminal (webshell), se desarrolla un _script_ automatizado en Python haciendo uso de la librería de procesamiento de imágenes `Pillow` (`PIL`).
    
4. El algoritmo carga las matrices RGB de ambas imágenes y realiza una suma matemática a nivel de canal de color (R, G, B) para cada píxel individual.
    
5. Para evitar desbordamientos de datos numéricos y lograr el contraste visual perfecto, se aplica la operación módulo 256 (`(canal1 + canal2) % 256`) sobre el resultado de la suma. Esta operación neutraliza el ruido estático de fondo y resalta los píxeles que conforman el texto original.
    
6. Tras ejecutar el _script_ y generar la imagen combinada (`bandera_revelada.png`), se convierte su contenido binario crudo a formato de texto utilizando el comando de terminal `base64`.
    
7. Utilizando el esquema de URI `data:image/png;base64,`, se pega la inmensa cadena de texto resultante en la barra de direcciones de un navegador web local. Esto obliga al navegador a renderizar el código al vuelo, permitiendo visualizar la imagen decodificada y leer el texto de la bandera sin necesidad de descargar archivos o usar visores gráficos tradicionales.
    

**Bandera:** `picoCTF{8cdf93c3}`
### Notas
**Herramientas utilizadas:** Intérprete de Python con la librería `Pillow` (`PIL`) para la manipulación matricial de los arreglos RGB, y la utilidad de terminal `base64` acoplada al renderizado nativo del navegador web.
### Referencias
