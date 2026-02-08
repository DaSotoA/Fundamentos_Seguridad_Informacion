### First Grep
### Descripcion
Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.The flag is in this [file](https://challenge-files.picoctf.net/c_fickle_tempest/2e9bfa4e1d90ac25a999fefdfb4feb8a2ff4eb73e4c61af4889a3762687ada01/file).
### Solucion
Usando Terminal de linux
```
dacid@LAPTOP-8H74K3S8:~$ grep -o "picoCTF{.*}" file
picoCTF{grep_is_good_to_find_things_29f42460}
```

picoCTF{grep_is_good_to_find_things_29f42460}

### Notas
- grep es una funcion para en un archivo buscar un contenido en especifico, el comando -o sirve para solo mostrar lo que se pide, y el .* significa que empieza con "{" y termina con "}".
### Referencias
- https://www.freecodecamp.org/espanol/news/grep-command-tutorial-how-to-search-for-a-file-in-linux-and-unix-with-recursive-find/