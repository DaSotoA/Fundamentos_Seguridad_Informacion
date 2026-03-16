### Printer Shares
### Descripcion
Oops! Someone accidentally sent an important file to a network printer—can you retrieve it from the print server?
The printer is on `60803`.you can try `$ nc -vz mysterious-sea.picoctf.net 60803`
### Solucion
- Se utilizó el cliente `smbclient` para listar (`-L`) los recursos compartidos en el servidor remoto, identificando una carpeta pública denominada `shares`.
- Se estableció una conexión al recurso compartido `//mysterious-sea.picoctf.net/shares` utilizando el parámetro `-N`, lo cual permitió el acceso sin necesidad de proporcionar una contraseña.
- Tras listar el contenido del directorio con `ls`, se identificó el archivo `flag.txt` y se transfirió a la máquina local mediante el comando `get`.
- Una vez cerrada la sesión de SMB, se utilizó el comando `cat` en la terminal local para visualizar el contenido del archivo descargado y obtener la bandera.
```
davidSoA-picoctf@webshell:~$ smbclient -L //mysterious-sea.picoctf.net -p 60803 -N

        Sharename       Type      Comment
        ---------       ----      -------
        shares          Disk      Public Share With Guests
        IPC$            IPC       IPC Service (Samba 4.19.5-Ubuntu)
SMB1 disabled -- no workgroup available
davidSoA-picoctf@webshell:~$ smbclient //mysterious-sea.picoctf.net/shares -p 60803 -N
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Fri Mar  6 20:25:45 2026
  ..                                  D        0  Fri Mar  6 20:25:45 2026
  dummy.txt                           N     1142  Wed Feb  4 21:22:17 2026
  flag.txt                            N       37  Fri Mar  6 20:25:45 2026

                65536 blocks of size 1024. 56896 blocks available
smb: \> get flag.txt
getting file \flag.txt of size 37 as flag.txt (12.0 KiloBytes/sec) (average 12.0 KiloBytes/sec)
smb: \> exit
davidSoA-picoctf@webshell:~$ cat flag.txt 
```
**picoCTF{5mb_pr1nter_5h4re5_7a400ec3}**
### Notas
- SMB (Server Message Block) es un protocolo de red utilizado para compartir archivos, impresoras y puertos serie entre nodos de una red.
### Referencias