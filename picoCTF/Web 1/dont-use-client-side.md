### dont-use-client-side
### Descripcion
Can you break into this super secure portal?http://fickle-tempest.picoctf.net:63934
### Solucion
- Con el debugger en el archivo index
```
if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == 'eb02') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_2') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'b45}') {
                  alert("Password Verified")
```
picoCTF{no_clients_plz_2eb02b45}
### Notas
- Se ordena dependiendo de los valores
### Referencias