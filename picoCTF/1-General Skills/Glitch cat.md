### Glitch cat
### Descripcion
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 60267`
### Solucion
Usando Terminal
```
dacid@LAPTOP-8H74K3S8:~$ nc saturn.picoctf.net 60267
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
^C
dacid@LAPTOP-8H74K3S8:~$ python3
Python 3.12.3 (main, Apr 10 2024, 05:33:47) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')
picoCTF{gl17ch_m3_n07_bda68f75}
```

picoCTF{gl17ch_m3_n07_bda68f75}

### Notas
- Con python se puede traducir el codigo ASCII
### Referencias
- Terminal de Ubuntu 