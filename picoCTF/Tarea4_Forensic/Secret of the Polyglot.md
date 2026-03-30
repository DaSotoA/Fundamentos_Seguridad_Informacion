### Secret of the Polyglot
### Descripcion
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/98/flag2of2-final.pdf).
### Solucion
- Se descarga el archivo proporcionado en las instrucciones (nombrado comúnmente `flag2of2-final.pdf`).
    
- Al abrir el archivo con un visor de PDF convencional, el documento renderiza un texto que contiene la segunda parte de la bandera: `1n_pn9_&_pdf_90974127}`.
    
- Para buscar la primera mitad, se procede a inspeccionar el código fuente a bajo nivel del archivo utilizando un editor hexadecimal (se puede emplear una herramienta web como HexEd.it o comandos de terminal en Linux como `xxd` o `hexdump`).
    
- Al revisar los primeros bytes del archivo (la cabecera), se identifica inmediatamente la firma característica de un archivo de imagen: los caracteres `PNG`. Esto revela que el documento oculta información de imagen.
    
- Sabiendo esto, se modifica la extensión del archivo, renombrándolo de `flag2of2-final.pdf` a `flag2of2-final.png`.
    
- Al abrir el archivo renombrado en un visor de imágenes, el intérprete ignora el texto del PDF y renderiza la capa visual, mostrando una imagen que contiene la primera mitad de la bandera: `picoCTF{f1u3n7_`.
    
- Finalmente, se concatenan ambas cadenas de texto para formar la respuesta.

picoCTF{f1u3n7_1n_pn9_&_pdf_1f991f77}
### Notas
### Referencias
