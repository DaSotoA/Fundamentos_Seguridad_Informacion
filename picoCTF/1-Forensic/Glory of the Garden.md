### Glory of the Garden
### Descripcion
This file contains more than it seems.
Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/19722024edeecca10f263776ab05c8b1235b136dcf25aa6e976d3860513ffcd5/garden.jpg).
### Solucion
```
┌──(kali㉿kali)-[~/forensic/gloryofthegarden]
└─$ strings -n 13 garden.jpg | grep picoCTF
Here is a flag: picoCTF{more_than_m33ts_the_3y37fde8891}

```
### Notas
- En el hexeditor se puede ver todo el codigo tras la imagen en formato de hexadecimal.
### Referencias