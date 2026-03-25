### Operation Orchid
### Descripcion
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/212/disk.flag.img.gz)
### Solucion
- Se descarga la imagen de disco comprimida (`disk.flag.img.gz`) y se extrae utilizando el comando `gunzip disk.flag.img.gz` para obtener la imagen en bruto `disk.flag.img`.
    
- Se examina la estructura de particiones de la imagen mediante el comando `mmls disk.flag.img`. La salida revela múltiples particiones; la que resulta de mayor interés es la partición número 4, identificada como Linux (0x83), la cual inicia en el _offset_ `411648`.
    
- Se listan los archivos y directorios de esta partición buscando coincidencias con la palabra clave "flag" mediante el comando: `fls -rp -o 411648 disk.flag.img | grep -i flag.txt` _(Esto revela que existe un archivo cifrado llamado `flag.txt.enc` y un archivo `flag.txt` que marca haber sido eliminado)_.
    
- Para entender qué sucedió, se lista todo el directorio `/root` utilizando `fls -rp -o 411648 disk.flag.img | grep -i "root/"`. Esto revela un archivo de historial de comandos llamado `.ash_history` (con el inodo `1875`).
    
- Se lee el contenido del historial utilizando `icat -o 411648 disk.flag.img 1875`. El historial muestra exactamente cómo se cifró la bandera: `openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567` También indica que, posterior al cifrado, el archivo original en texto plano fue destruido permanentemente usando el comando `shred`.
    
- Ya que el archivo original es irrecuperable por métodos normales, la única opción es extraer la versión cifrada. Se extrae el archivo `flag.txt.enc` (inodo `1782`) a la máquina local: `icat -o 411648 disk.flag.img 1782 > flag.txt.enc`
    
- Utilizando la contraseña descubierta en el historial (`unbreakablepassword1234567`), se emplea la herramienta OpenSSL para realizar la operación inversa (descifrado) agregando la bandera `-d` y cambiando las posiciones de entrada y salida: `openssl aes256 -d -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567`
    
- Se lee el archivo `flag.txt` resultante para visualizar la bandera.

picoCTF{h4un71ng_p457_0a710765}  
### Notas
**Herramientas utilizadas:** Utilidades de The Sleuth Kit (`mmls`, `fls`, `icat`), herramienta de descompresión (`gunzip`) y la suite de criptografía (`openssl`).
### Referencias
