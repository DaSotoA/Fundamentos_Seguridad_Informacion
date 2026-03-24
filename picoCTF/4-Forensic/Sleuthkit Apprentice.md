### Sleuthkit Apprentice
### Descripcion
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/137/disk.flag.img.gz)
### Solucion
- Se descarga y extrae el archivo de la imagen de disco ejecutando el comando `gzip -d disk.flag.img.gz`.
- Se utiliza `mmls disk.flag.img` para listar las particiones y encontrar el "Offset" (punto de inicio) de la partición principal de Linux.
- El usuario emplea el comando `fls -o [offset] disk.flag.img` para listar los archivos y directorios ubicados en la raíz de ese sistema de archivos.
- Se identifica el número de inodo (inode) de los directorios clave, como el directorio `/root`. El participante navega a través de las carpetas especificando el inodo en su búsqueda mediante el comando `fls -o [offset] disk.flag.img [inodo]`.
- Una vez que se localiza el archivo que contiene la bandera (generalmente alojado en una ruta como `/root/my_folder/flag.txt`), se utiliza el comando `icat -o [offset] disk.flag.img [inodo_del_archivo]` para leer el contenido de ese archivo específico directamente desde el disco y obtener la bandera final.
picoCTF{by73_5urf3r_adac6cb4}
### Notas
**Herramientas utilizadas:** `mmls` (para ubicar las particiones y offsets), `fls` (para listar archivos y directorios dentro de una partición específica) e `icat` (para extraer y leer el contenido de un archivo basándose en su número de inodo).
### Referencias