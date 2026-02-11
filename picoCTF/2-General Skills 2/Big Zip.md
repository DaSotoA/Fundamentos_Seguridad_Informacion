### Big Zip
### Descripcion
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)
### Solucion
- Terminal, se usa la funcion grep para la busqueda con -r para que asi pueda buscar en todas las subcarpetas para buscar la palabra deseada.
```
davidSoA-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/504/big-zip-files.zip
davidSoA-picoctf@webshell:~$ unzip big-zip-files.zip
davidSoA-picoctf@webshell:~$ grep -r "picoCTF"
README.txt:Welcome to the picoCTF webshell!
README.txt:picoCTF challenges.
README.txt:  Extensive brute-forcing is not necessary to solve picoCTF challenges.
README.txt:- If you change your username through the picoCTF website, you will
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```

picoCTF{gr3p_15_m4g1c_ef8790dc}

### Notas
La funcion -r se usa para buscar en carpetas la informacion deseada
### Referencias

