### Strings it
### Descripcion
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/6577d3f1500aebcd300787bd5d96216b30aed379c811f5e83e888f897da4a3d5/strings) without running it?
### Solucion
- Con la funcion strings
```
davidSoA-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/6577d3f1500aebcd300787bd5d96216b30aed379c811f5e83e888f897da4a3d5/strings
davidSoA-picoctf@webshell:~$ strings strings | grep "picoCTF"
picoCTF{5tRIng5_1T_d6306c19}
```

picoCTF{5tRIng5_1T_d6306c19}
### Notas
- La funcio strings convierte e texto binario a una cadena para poder buscar la informacion requerida.
### Referencias
