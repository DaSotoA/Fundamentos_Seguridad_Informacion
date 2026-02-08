### Nice netcat...
### Descripcion
- There is a nice program that you can talk to by using this command in a shell:$ nc wily-courier.picoctf.net 55171, but it doesn't speak English...
### Solucion
Terminal de ubuntu
```
nc wily-courier.picoctf.net 55171
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
100
53
100
56
56
125
10
```
Despues un traductor de ASCII a texto
https://es.rakko.tools/tools/76/
picoCTF{g00d_k1tty!_n1c3_k1tty!_d5d88}

- ### Solucion 2 usando solo terminal
```
dacid@LAPTOP-8H74K3S8:~$ nc wily-courier.picoctf.net 61137 | awk '{printf "%c", $1}'
picoCTF{g00d_k1tty!_n1c3_k1tty!_d5d88}
```
picoCTF{g00d_k1tty!_n1c3_k1tty!_d5d88}

### Notas
- El codigo ASCII representa letras que se pueden traducir.
- - **`nc ...`**: Trae los números (112, 105, 99...).
- **`|`**: Pasa esos números al siguiente comando.
- **`awk '{printf "%c", $1}'`**:
    - Toma cada número (`$1`).
    - Lo formatea como un **carácter** (`%c`), que es básicamente convertirlo de Decimal a ASCII automáticamente.
	- Lo imprime sin saltos de línea.
### Referencias
- https://es.rakko.tools/tools/76/ (solucion 1)
- https://gemini.google.com/app/76ef49a91caf257a?hl=es (solucion 2)