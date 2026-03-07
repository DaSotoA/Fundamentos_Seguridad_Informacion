### Local Authority
### Descripcion
Can you get the flag?
Go to this [website](http://saturn.picoctf.net:62742/) and see what you can discover.
### Solucion
- Aqui se da login con cualquier contraseña y usuario, luego se inspecciona, se dirije al sources, para despues abrir el codigo de secure.js y ahi nos da la contraseña y usuario correcto
```
- if( username === 'admin' && password === 'strongPassword098765' )
```
picoCTF{j5_15_7r4n5p4r3n7_a8788e61}
### Notas
### Referencias