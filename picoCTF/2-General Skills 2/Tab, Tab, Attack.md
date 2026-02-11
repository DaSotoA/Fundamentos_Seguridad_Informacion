###  Tab, Tab, Attack
### Descripcion
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.[Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip)
### Solucion
```
davidSoA-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip
davidSoA-picoctf@webshell:~$ unzip Addadshashanammu.zip 
davidSoA-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/  
davidSoA-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c
davidSoA-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep "picoCTF"
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}
```
### Notas
- Con tab solo basta poner 2 o 3 letras para poder poner los nombres de los archivos.
### Referencias
