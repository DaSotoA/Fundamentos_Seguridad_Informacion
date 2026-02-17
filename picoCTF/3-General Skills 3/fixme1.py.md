### fixme1.py
### Descripcion
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)
### Solucion
- Quitar identacion.
```
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06>

  
flag = str_xor(flag_enc, 'enkidu')
print(f'That is correct! Heres your flag: {flag}' )
```

```
davidSoA-picoctf@webshell:~$ nano fixme1.py 
davidSoA-picoctf@webshell:~$ python fixme1.py 
That is correct! Heres your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
```
picoCTF{1nd3nt1ty_cr1515_6a476c8f}
### Notas
### Referencias