### Descripción

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Binary%20Digits.md#descripci%C3%B3n)

This file doesn't look like much... just a bunch of 1s and 0s. But maybe it's not just random noise. Can you recover anything meaningful from this?Download the file [here](https://challenge-files.picoctf.net/c_plain_mesa/8fa300f2ce84eca8cf2b18d1bd0c9cd92c888b09d838e2462c4edd30d951da59/digits.bin).

### Solución

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Binary%20Digits.md#soluci%C3%B3n)

- Descargamos el archivo
    
    Primero, **bajamos** el archivo binario directamente a nuestra carpeta de trabajo:
    

```
wget -q https://challenge-files.picoctf.net/c_plain_mesa/8fa300f2ce84eca8cf2b18d1bd0c9cd92c888b09d838e2462c4edd30d951da59/digits.bin
```

- Creamos el script de conversión
    
    Luego, **escribimos** un script en Python que toma esos ceros y unos, los agrupa en bloques de 8 bits y los transforma en bytes reales para reconstruir la imagen JPG
    

```
with open('digits.bin', 'r') as f:
    data = f.read().strip()

byte_data = bytearray()
for i in range(0, len(data), 8):
    byte_data.append(int(data[i:i+8], 2))

with open('resultado.jpg', 'wb') as f:
    f.write(byte_data)
```

- Ejecutamos y visualizamos el flag

Finalmente, **corrimos** nuestro código y **abrimos** el archivo resultante para leer la bandera:

```
python3 solve.py
xdg-open resultado.jpg
```

picoCTF{h1dd3n_1n_th3_b1n4ry_8d00e35f}