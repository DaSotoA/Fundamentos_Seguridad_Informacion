### hideme
### Descripcion
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/257/flag.png).
### Solucion
- Se descarga el archivo de imagen proporcionado en las instrucciones del reto.
    
- Como primer paso de análisis, se verifica la integridad y el tipo real de archivo en la terminal utilizando el comando `file` para confirmar que su estructura corresponde efectivamente a un formato de imagen PNG válido.
    
- Sospechando que la imagen contiene información adjunta, se utiliza una herramienta forense de "tallado de datos" (_file carving_) como `foremost` o `binwalk` para buscar firmas de otros archivos incrustadas en el código hexadecimal de la imagen.
    
- Al procesar el archivo original (por ejemplo, ejecutando `foremost imagen.png`), el programa logra identificar y extraer de forma automatizada un archivo comprimido en formato ZIP que estaba oculto dentro de la imagen.
    
- Se procede a extraer el contenido de este nuevo archivo ZIP utilizando utilidades de descompresión estándar en la terminal (como `7z x` o `unzip`).
    
- La descompresión revela una carpeta oculta llamada `secret`, dentro de la cual se encuentra un segundo archivo de imagen llamado `flag.png`.
    
- Finalmente, al abrir este último archivo (`flag.png`) con cualquier visor de imágenes gráfico (o utilizando el comando `xdg-open`), se puede observar el texto de la bandera impreso visualmente en el centro de la imagen.

picoCIF{Hiddinng_An_imag3_within_@n_ima9e_dc2ab58f}
### Notas
### Referencias
