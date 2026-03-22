Proper session timeout controls are critical for securing user accounts. If a user logs in on a public or shared computer but doesn’t explicitly log out (instead simply closing the browser tab), and session expiration dates are misconfigured, the session may remain active indefinitely.This then allows an attacker using the same browser later to access the user’s account without needing credentials, exploiting the fact that sessions never expire and remain authenticated.Your friend tells you to check out a new social media platform he built a few years ago. Although its still under development, he said the site is almost complete. He also mentioned that he hates constantly logging into sites, and so has made his page that 'once you login, you never have to log-out again'!Browse [here](http://dolphin-cove.picoctf.net:65298/), and find the flag!

### Solución

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Old%20Sessions.md#soluci%C3%B3n)

Se pone /sessions al final de la ruta. !Eso nos lleva a

```
1) session:OqSzSZb5_4qOJEdw04JVb4DFzGIzDBh-Qj1XyvAblcY, {'_permanent': True, 'key': 'admin'}

2) session:BFGao5NANhxjqURnR4qiRMoENGDdDpqW57cDBqTwBLc, {'_permanent': True, 'key': 'dani'}
```

solo copiamos el valor de la cookie de admin, editamos nuestra cookie session y refrescamos la página, lo que nos da la flag.

picoCTF{s3t_s3ss10n_3xp1rat10n5_ed8964c2}

### Notas

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Old%20Sessions.md#notas)

se usó cookie editor.