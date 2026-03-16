### SUDO MAKE ME A SANDWICH
### Descripcion
Can you read the flag? I think you can!
`ssh -p 65435 ctf-player@green-hill.picoctf.net` using password `f7e73aca`
### Solucion
1. Usamos `sudo -l` y descubrimos que se tenía permiso para ejecutar **Emacs** como root sin contraseña.
2. Como Emacs puede abrir cualquier archivo si se corre como root, se usa para leer el archivo restringido.
3. Ejecutamos Emacs en **modo batch** (sin interfaz) para que insertara el contenido de `flag.txt` y lo imprimiera directamente en la terminal.
```
ctf-player@challenge:~$ sudo emacs --batch --quick --insert "flag.txt" --eval '(princ (buffer-string))'
```
**picoCTF{ju57_5ud0_17_9418380d}**  
### Notas
- Emacs es un editor de texto extremadamente avanzado y flexible que incluye su propio intérprete de lenguaje.
### Referencias