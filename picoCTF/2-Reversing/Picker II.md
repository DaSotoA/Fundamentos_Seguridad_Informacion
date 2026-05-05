### Picker II
### Descripcion
Can you figure out how this program works to get the flag?
Connect to the program with netcat:`$ nc saturn.picoctf.net 53201`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/521/picker-II.py).
### Solucion
- Se analiza el filtro y se determina que, aunque la función `win` está bloqueada, la vulnerabilidad subyacente de `eval()` sigue existiendo.
    
- Dado que `eval()` ejecuta código Python de forma nativa, se puede interactuar directamente con el sistema operativo sin necesidad de llamar a la función bloqueada.
    
- El _payload_ exacto ingresado en el servidor es: `print(open('flag.txt').read())`

picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_b924e8e5}
### Notas
### Referencias