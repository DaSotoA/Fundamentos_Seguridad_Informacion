### Redaction gone wrong
### Descripcion
Now you DON’T see me.
This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
### Solucion
- Se descarga el archivo PDF del reporte. Al visualizarlo en un lector de documentos estándar, se pueden observar grandes bloques negros que cubren partes del texto, simulando una censura de información sensible.
    
- Como experimento inicial (según la metodología descrita en el artículo base), se puede intentar convertir el PDF a un archivo de procesamiento de texto (como Word) para intentar mover los cuadros negros. Sin embargo, este método gráfico no siempre arroja los resultados deseados.
    
- La forma más eficaz de aprovechar esta vulnerabilidad de "mala censura" es abrir el PDF original, seleccionar manualmente todo el contenido del documento (utilizando el atajo `Ctrl+A` o arrastrando el cursor) y copiarlo al portapapeles.
    
- Acto seguido, se pega el contenido copiado en cualquier editor de texto plano, como el Bloc de notas (_Notepad_). Al hacer esto, el texto original que se encontraba "oculto" bajo las cajas negras se pegará en formato de texto claro, revelando la bandera completa sin el obstáculo gráfico.

picoCTF{C4n_Y0u_S33_m3_fully}
### Notas
### Referencias
