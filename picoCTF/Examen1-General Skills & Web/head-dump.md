### head-dump
### Descripcion
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.
The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.
The website is running [picoCTF News](http://verbal-sleep.picoctf.net:57479/).
### Solucion
- Se analiza la pagina se va a la parte de API, se analiza los problemas y con cat y grep conseguimos la bandera
```
┌──(kali㉿kali)-[~]
└─$ cd Downloads 
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ cat heapdump-1773628305517.heapsnapshot| grep "picoCTF"
picoCTF{Pat!3nt_15_Th3_K3y_59106086}

```
picoCTF{Pat!3nt_15_Th3_K3y_59106086}
### Notas
### Referencias
