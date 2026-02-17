### fixme2.py
### Descripcion
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)
### Solucion
```
davidSoA-picoctf@webshell:~$ python fixme2.py 
  File "/home/davidSoA-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
davidSoA-picoctf@webshell:~$ nano fixme2.py 
davidSoA-picoctf@webshell:~$ python fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```
picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
### Notas
### Referencias
