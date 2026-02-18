### Special
### Descripcion
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 62972 ctf-player@saturn.picoctf.net`The password is `483e80d4`
### Solucion
```
davidSoA-picoctf@webshell:~$ ssh -p 62972 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62972 ([13.59.203.175]:62972)' can't be established.
ED25519 key fingerprint is SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62972' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.8.0-1044-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Special$ ls
Is 
sh: 1: Is: not found
Special$ ?
? 
sh: 1: ?: not found
Special$ flag
Flag 
sh: 1: Flag: not found
Special$ TM
To 
sh: 1: To: not found
Special$ Is
Is 
sh: 1: Is: not found
Special$ Clear
Clear 
sh: 1: Clear: not found
Special$ Clear & find .
Clear & find . 
sh: 1: Clear: not found
.
./blargh
./blargh/flag.txt
./.cache
./.cache/motd.legal-displayed
Special$ Clear & cat ./blargh/flag.txt
Clear & cat ./blargh/flag.txt 
sh: 1: Clear: not found
picoCTF{5p311ch3ck_15_7h3_w0r57_b741d1b1}
```

picoCTF{5p311ch3ck_15_7h3_w0r57_b741d1b1}
### Notas
- Al usar el operador **`&`**, se engaña al filtro del sistema: mientras el programa intentaba "corregir" la primera palabra (como `Clear`), la shell de Linux ejecutaba la segunda instrucción (`find` o `cat`) de forma independiente.
### Referencias
- https://youtu.be/6lEd1yVsxpw
