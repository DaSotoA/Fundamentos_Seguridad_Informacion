### St3g0
### Descripcion
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)
### Solucion
- Se descarga el archivo de imagen adjunto en las instrucciones del desafío.
    
- Como buena práctica inicial, se recomienda realizar un análisis superficial utilizando comandos de terminal como `strings` o lectores de metadatos (como `exiftool`) para buscar texto en plano. En este escenario, la exploración básica no arroja información útil.
    
- Se procede a inspeccionar la imagen mediante herramientas de análisis visual de planos de bits, como la plataforma web _StegOnline_. Al aislar los canales de color (RGB) y visualizar específicamente el nivel de bit `0` (el bit menos significativo), se observan patrones anómalos y ruido visual concentrado en la esquina superior izquierda de la imagen, indicando la presencia de datos inyectados.
    
- Confirmada la existencia de esteganografía a nivel de bits, se recurre a `zsteg`, una utilidad avanzada de línea de comandos en Linux diseñada para detectar y extraer automáticamente datos ocultos en imágenes PNG y BMP.
    
- Se ejecuta el escaneo pasando como argumento el archivo del reto: `zsteg archivo_del_reto.png`
    
- La herramienta itera sobre las diferentes combinaciones de planos de bits y flujos de datos. Entre los resultados arrojados en la consola, se imprimirá la carga útil extraída en formato de texto plano, revelando la bandera.

picoCTF{7h3r3_15_n0_5p00n_a1062667}
### Notas
**Herramientas utilizadas:** Analizador visual web (`StegOnline`) y extractor esteganográfico automatizado (`zsteg`).
### Referencias
