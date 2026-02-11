### Based
### Descripcion
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?Connect with nc fickle-tempest.picoctf.net 59568.
### Solucion
- Con cyberchef
```
davidSoA-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 63638
Let us see how data is stored
falcon
Please give the 01100110 01100001 01101100 01100011 01101111 01101110 as a word.
...
you have 45 seconds.....

Input:
falcon
Please give me the  o163 o154 o165 o144 o147 o145 as a word.
Input:
sludge
Please give me the 6c616d70 as a word.
Input:
lamp
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_563BAF26}
```
### Notas
- Se tradujo todo con cyberchef
### Referencias
- https://cyberchef.io/#recipe=From_Binary('Space',8/disabled)From_Octal('Space'/disabled)From_Hex('Auto')&input=NmM2MTZkNzA
