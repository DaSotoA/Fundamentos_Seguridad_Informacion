### Descripción

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/DISKO%204.md#descripci%C3%B3n)

Can you find the flag in this disk image? This time I deleted the file! Let see you get it now!Download the disk image [here](https://challenge-files.picoctf.net/c_plain_mesa/c7ab8389098be28cbd419686b9ec4a2b969a06ecd0e11cb9ae6af9acf4e063b1/disko-4.dd.gz).

### Solución

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/DISKO%204.md#soluci%C3%B3n)

- Descargamos el archivo de la imagen de disco directamente desde el enlace del reto

```
wget https://challenge-files.picoctf.net/c_plain_mesa/c7ab8389098be28cbd419686b9ec4a2b969a06ecd0e11cb9ae6af9acf4e063b1/disko-4.dd.gz
```

- Descomprimimos el archivo para obtener la imagen cruda

```
gunzip disko-4.dd.gz
```

- Listamos los archivos del sistema buscando aquellos marcados con un asterisco, lo que indica que fueron eliminados pero sus datos siguen en el disco

```
fls -r disko-4.dd | grep "\*"
```

- Identificamos el archivo borrado dont-delete.gz con el inodo 532021 y extrajimos su contenido a un nuevo archivo comprimido

```
icat disko-4.dd 532021 > recuperado.gz
```

- Descomprimimos el archivo recuperado y leímos su contenido para visualizar la bandera

```
gunzip recuperado.gz
cat recuperado
```

la bandera final es

- picoCTF{d3l_d0n7_h1d3_w3ll_c405de7d}