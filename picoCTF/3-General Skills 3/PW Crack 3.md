### PW Crack 3
### Descripcion
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
### Solucion
- agregar un for para probar las opciones
```
def level_3_pw_check():
    pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]

   # user_pw = input("Please enter correct password for flag: ")
    for user_pw in pos_pw_list:
         user_pw_hash = hash_pw(user_pw)
    
         if( user_pw_hash == correct_pw_hash ):
                 print("Welcome back... your flag, user:")
                 decryption = str_xor(flag_enc.decode(), user_pw)
                 print(decryption)
    return
```
```
davidSoA-picoctf@webshell:~$ nano level3.py 
davidSoA-picoctf@webshell:~$ python level3.py 
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
```
### Notas
### Referencias