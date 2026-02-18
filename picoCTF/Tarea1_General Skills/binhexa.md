### binhexa
### Descripcion
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 49802`
### Solucion
```
davidSoA-picoctf@webshell:~$ nc titan.picoctf.net 49802

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11000001
Binary Number 2: 01111011


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100111100
Correct!

Question 2/6:
Operation 2: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01000001
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111011
Correct!

Question 4/6:
Operation 4: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 110000010
Correct!

Question 5/6:
Operation 5: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0101110010111011
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00111101
Correct!

Enter the results of the last operation in hexadecimal: 3D

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
```

picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
### Notas
### Referencias
Para multiplicacion https://www.calculator.net/binary-calculator.html?number1=11000001&c2op=%2B&number2=01111011&calctype=op&x=Calculate