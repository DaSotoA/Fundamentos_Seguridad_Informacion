### WhitePages
### Descripcion
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/ab5453de03105a8aab9c68b0b46e66a4fe0a781c3915ab519f7fab31b3ce6894/whitepages.txt) is all blank!
### Solucion
- Verificamos que el archivo es UTF-8 con lineas largas

`file whitepages.txt`

- Visualizamos el hexdump del archivo y vemos que es una seuencia de caracteres unicode (e2 80 83 y 20 )

`xxd -g 1 -l 100 whitepages.txt`

- Reemplazamos e2 80 83 por 0s y 20 por 1s

`sed 's/\xe2\x80\x83/0/g' whitepages.txt | sed 's/\x20/1/g'`

- Convertimos los 0s y 1s a caracteres y tendremos la bandera.

picoCTF{not_all_spaces_are_created_equal_bbc4f54c75763bd78dc840f05eb7a752}
### Notas
### Referencias