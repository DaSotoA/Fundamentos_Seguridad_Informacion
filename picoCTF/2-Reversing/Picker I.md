### Picker I
### Descripcion
This service can provide you with a random number, but can it do anything else?
Connect to the program with netcat:`$ nc saturn.picoctf.net 55582`
The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/513/picker-I.py).
### Solucion
- Al analizar el código fuente proporcionado, se identifica una función previamente definida llamada `win()`, la cual abre el archivo `flag.txt` y lo imprime en pantalla.
    
- Al conectarse al servidor mediante `nc`, se ingresa directamente el nombre de la función como _input_.
    
- El _payload_ exacto es: `win`


picoCTF{4_d14m0nd_1n_7h3_r0ugh_b523b2a1}
### Notas
### Referencias