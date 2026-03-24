### Sleuthkit Intro
### Descripcion
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)Access checker program: `nc saturn.picoctf.net 62617`
### Solucion
1. Se descarga el archivo de imagen de disco comprimido y se extrae utilizando el comando `gzip -d disk.img.gz`.
2. Se ejecuta el comando `mmls disk.img` para analizar la estructura de particiones del disco.
3. En la tabla de resultados, el usuario identifica la partición descrita como "Linux (0x83)" y anota el valor de su longitud (columna "Length"). Por ejemplo, un valor común podría ser `202752`.
4. El participante se conecta al servidor proporcionado en el reto usando netcat en la terminal: `nc saturn.picoctf.net [puerto]`.
5. El servidor solicita el tamaño de la partición. Se ingresa el valor de la longitud obtenido previamente y la terminal devuelve la bandera.
`picoCTF{mm15_f7w!}`
### Notas
**Herramientas utilizadas:** `mmls` (parte del paquete The Sleuth Kit) para mostrar el diseño de las particiones del volumen, y `nc` (Netcat) para establecer la conexión con el servidor.
### Referencias