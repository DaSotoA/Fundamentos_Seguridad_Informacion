### Time Machine
### Descripcion
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/66/challenge.zip)
### Solucion
```
davidSoA-picoctf@webshell:~$ cd drop-in/
davidSoA-picoctf@webshell:~/drop-in$ ls
exit  flag.py  message.py  message.txt
davidSoA-picoctf@webshell:~/drop-in$ cat message.txt
This is what I was working on, but I'd need to look at my commit history to know why...
```
```
commit 3339c144a0c78dc2fbd3403d2fb37d3830be5d94 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:22 2024 +0000

    picoCTF{t1m3m@ch1n3_d3161c0f}
```
### Notas
- git log ayuda a ver los comits pasados.
### Referencias
- https://primer.picoctf.org/#_git_version_control