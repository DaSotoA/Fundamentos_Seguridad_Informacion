### JaWT Scratchpad 
### Descripcion
Check the admin scratchpad!http://fickle-tempest.picoctf.net:57922
### Solucion
- Nos logueamos con cualquier usuario
- Copiamos el token jwt a un archivo llamado token
- Lo crackeamos en kali usando john con el diccionario rockyou.txt
`gizip -d /usr/share/wordlists/rockyou.txt.gz john token -w=/usr/share/wordlists/rockyou.txt`
- vamos al sitio jwt debuger, y modificamos el payload por admin
- ponemos la palabra crackeada en la firma
- copiamos el nuevo token generado a la cookie y recargamos la pagina
```
- JSON: [https://en.wikipedia.org/wiki/JSON](https://en.wikipedia.org/wiki/JSON "https://en.wikipedia.org/wiki/JSON")
- JWT : [https://jwt.io/introduction](https://jwt.io/introduction "https://jwt.io/introduction")
- jwt debugger : [https://jwt.lannysport.net/](https://jwt.lannysport.net/ "https://jwt.lannysport.net/")
- john : [https://github.com/openwall/john](https://github.com/openwall/john "https://github.com/openwall/john")
```
### Notas
- Con Jonh se prueban muchas contraseñas por segundo y asi se soluciona.
### Referencias
- JSON: [https://en.wikipedia.org/wiki/JSON](https://en.wikipedia.org/wiki/JSON "https://en.wikipedia.org/wiki/JSON")
- JWT : [https://jwt.io/introduction](https://jwt.io/introduction "https://jwt.io/introduction")
- jwt debugger : [https://jwt.lannysport.net/](https://jwt.lannysport.net/ "https://jwt.lannysport.net/")
- john : [https://github.com/openwall/john](https://github.com/openwall/john "https://github.com/openwall/john")
