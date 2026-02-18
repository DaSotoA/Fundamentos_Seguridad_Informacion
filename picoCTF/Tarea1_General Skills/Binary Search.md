### Binary Search
### Descripcion
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/18/challenge.zip)

`ssh -p 50844 ctf-player@atlas.picoctf.net`Using the password `84b12bae`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
### Solucion
```
davidSoA-picoctf@webshell:~$ ssh -p 50844 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:50844 ([18.217.83.136]:50844)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:50844' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 200
Higher! Try again.
Enter your guess: 300
Lower! Try again.
Enter your guess: 250
Lower! Try again.
Enter your guess: 220
Lower! Try again.
Enter your guess: 210
Higher! Try again.
Enter your guess: 215
Higher! Try again.
Enter your guess: 218
Lower! Try again.
Enter your guess: 217
Lower! Try again.
Enter your guess: 216
Congratulations! You guessed the correct number: 216
Here's your flag: picoCTF{g00d_gu355_2e90d29b}
Connection to atlas.picoctf.net closed.
```

picoCTF{g00d_gu355_2e90d29b}
### Notas
### Referencias