### Scan Surprise
### Descripcion
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/14/challenge.zip)
The same files are accessible via SSH here:`ssh -p 57646 ctf-player@atlas.picoctf.net`Using the password `84b12bae`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
### Solucion
1. Se descarga y extrae el archivo del reto en la máquina local o entorno de trabajo.
    
2. Al explorar el directorio resultante (frecuentemente llamado `drop-in`), se identifica el archivo `flag.png` utilizando comandos básicos de listar directorios como `ls`.
    
3. Al inspeccionar la imagen, se comprueba que se trata de un código QR. Aunque es posible escanearlo utilizando la cámara de un dispositivo móvil, el enfoque técnico ideal en un entorno de consola (CLI) es utilizar un decodificador de imágenes por línea de comandos.
    
4. Se emplea la utilidad `zbarimg` (parte del paquete `zbar-tools` en Linux), la cual está diseñada para leer y decodificar códigos de barras y códigos QR directamente desde archivos de imagen.
    
5. Se ejecuta el comando apuntando hacia el archivo: `zbarimg flag.png`
    
6. La herramienta escanea la imagen, extrae la carga útil (_payload_) del código y devuelve el texto plano en la terminal, revelando así la bandera completa.

**Bandera:** `picoCTF{p33k_@_b00_0194a007}`
### Notas
### Referencias
