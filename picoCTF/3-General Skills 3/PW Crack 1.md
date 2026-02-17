### PW Crack 1
### Descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.
### Solucion
```
davidSoA-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 
That password is incorrect
davidSoA-picoctf@webshell:~$ nano level1.py
davidSoA-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
```
### Notas
### Referencias