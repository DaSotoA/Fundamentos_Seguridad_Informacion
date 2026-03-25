### Operation Oni
### Descripcion
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/70/disk.img.gz)
- Remote machine: `ssh -i key_file -p 52530 ctf-player@saturn.picoctf.net`
### Solucion
- Se descarga la imagen de disco comprimida (`disk.img.gz`) y se extrae su contenido utilizando el comando `gunzip disk.img.gz` para obtener el archivo `disk.img`.
    
- Se analiza la tabla de particiones del disco utilizando la herramienta `mmls disk.img`. La salida revela múltiples particiones, siendo la partición número 3 identificada como un sistema de archivos Linux (0x83) y la más extensa de todas. Se anota su _offset_ (punto de inicio).
    
- Utilizando el comando `fls -o [offset] disk.img`, se explora la raíz de dicha partición. El objetivo es buscar dentro del directorio de inicio del usuario principal (el directorio `/root`).
    
- Al listar el contenido del directorio `/root` (utilizando nuevamente `fls` con el inodo de dicha carpeta), se identifica un directorio oculto llamado `.ssh`. Dentro de `.ssh`, se encuentra un archivo de llave privada (como `id_rsa` o `id_ed25519`).
    
- Se anota el inodo de la llave privada y se extrae el archivo a la máquina local utilizando el comando `icat`: `icat -o [offset] disk.img [inodo_llave] > private_key`
    
- Por motivos de seguridad impuestos por SSH, los permisos de un archivo de llave privada deben ser restrictivos. Si los permisos son demasiado abiertos, SSH rechazará la llave. Por tanto, se cambian los permisos del archivo local con el comando `chmod 600 private_key`.
    
- Con la llave lista, el participante se conecta al servidor proporcionado en las instrucciones del reto utilizando el protocolo SSH, indicando explícitamente el uso del archivo de identidad: `ssh -i private_key ctf-player@[ip_del_servidor] -p [puerto]`
    
- Una vez dentro de la consola remota, un simple comando `ls` revelará el archivo de texto y, al leerlo con `cat flag.txt`, se obtendrá la bandera.

picoCTF{k3y_5l3u7h_b5066e83}
### Notas
**Herramientas utilizadas:** The Sleuth Kit (`mmls`, `fls`, `icat`), comandos de permisos (`chmod`) y cliente `ssh`.
### Referencias

