### Disk, disk, sleuth!
### Descripcion
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image.
[dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/ae15f331b193f3e33b88ebbd7a054b6d48af0e2d8b79c53805b3eeab7cf2c9e5/dds1-alpine.flag.img.gz)
### Solucion
1. Se descarga el archivo del reto y se extrae su contenido utilizando una herramienta de descompresión (por ejemplo, con el comando `gzip -d dds2-alpine.flag.img.gz`), obteniendo así el archivo de imagen en bruto `dds2-alpine.flag.img`.
2. Se analiza la tabla de particiones de la imagen mediante el comando `mmls`. En la salida generada por la terminal, se identifica el sector de inicio (_offset_) de la partición principal de Linux, el cual corresponde al valor `2048`: `mmls dds2-alpine.flag.img`
3. Se listan los archivos y directorios de la raíz de dicha partición utilizando el comando `fls`, especificando el _offset_ descubierto en el paso anterior: `fls -o 2048 dds2-alpine.flag.img`
4. Al explorar los inodos (_inodes_) listados, se inspecciona el contenido del directorio clave correspondiente (inodo `18290`). Dentro de los resultados de este directorio, se localiza el archivo de la bandera y se toma nota de su inodo asignado (`18291`): `fls -o 2048 dds2-alpine.flag.img 18290`
5. Finalmente, se extrae y lee el contenido directo del archivo utilizando el comando `icat`, indicando el formato en crudo, el tipo de sistema de archivos (`ext4`), el _offset_ (`2048`) y el inodo objetivo (`18291`): `icat -i raw -f ext4 -o 2048 dds2-alpine.flag.img 18291`
6. Al ejecutar la instrucción, el sistema procesa el bloque de datos e imprime la bandera directamente en la pantalla.

**Bandera:** `picoCTF{f0r3ns1c4t0r_n0v1ce_0ba8d02d}`
### Notas

### Referencias