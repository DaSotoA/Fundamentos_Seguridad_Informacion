### Lets Warm up...
### Descripcion
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
### Solucion
### Solucion 1 - usando cyberchef
https://cyberchef.io/#recipe=From_Hex('Auto')&input=MHg3MA

p

picoCTF{p}

### Solucion 2 - usando python
```
davidSoA-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x70)
112
>>> chr(112)
'p'
```

### Notas
- Cyberchef es una pagina que permite decodificar diferentes formatos.

### Referencias
- https://cyberchef.io/#recipe=From_Hex('Auto')&input=MHg3MA