### SQLiLite
### Descripcion
Can you login to this website?
Try to login [here](http://saturn.picoctf.net:64142/).
### Solucion
- Se inyectó `' OR 1=1 --` en el formulario para forzar una respuesta lógica verdadera en la base de datos, explotando la falta de limpieza en las entradas de texto.
- Despues se inspecciona en entwork y se encuentra la flag, en el html.
picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}
### Notas
### Referencias