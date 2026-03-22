### Descripción

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Timeline%200.md#descripci%C3%B3n)

Can you find the flag in this disk image? Wrap what you find in the picoCTF flag format.Download the disk image [here](https://challenge-files.picoctf.net/c_plain_mesa/aa1f8ba93409887e081435732d7037c45b30a8442853bf07c9e84fe4d0e0bc19/partition4.img.gz).

### Solución

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Timeline%200.md#soluci%C3%B3n)

- Descargamos el archivo comprimido y lo descomprimimos para obtener la imagen de la particion

```
wget -q https://challenge-files.picoctf.net/c_plain_mesa/aa1f8ba93409887e081435732d7037c45b30a8442853bf07c9e84fe4d0e0bc19/partition4.img.gz
gunzip partition4.img.gz
```

- Generamos un archivo con los metadatos de los archivos y despues creamos una linea de tiempo legible

```
fls -r -m / partition4.img > body
mactime -b body > timeline.txt
```

- Revisamos las primeras lineas de la linea de tiempo para encontrar fechas fuera de lo normal y localizamos el inodo 4945 en la ruta /bin/bcab con fecha de 1985

```
head -n 50 timeline.txt
```

- Extrajimos el contenido de ese inodo especifico y lo decodificamos de base64 para obtener el texto de la bandera

```
icat partition4.img 4945 | base64 -d
```

Resultado obtenido:*`71m311n3_0u7113r_h3r_43a2e7af` Flag final: `picoCTF{71m311n3_0u7113r_h3r_43a2e7af}`