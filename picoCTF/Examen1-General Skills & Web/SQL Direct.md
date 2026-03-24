### SQL Direct
### Descripcion
Connect to this PostgreSQL server and find the flag! 
`psql -h saturn.picoctf.net -p 64828 -U postgres pico` 
Password is `postgres`
### Solucion
- Primero, intentamos conectarnos al servidor de base de datos PostgreSQL usando el comando psql con el host, el puerto y el usuario que nos dieron.
    
- Como no teníamos instalada la herramienta necesaria en nuestra terminal de Kali, ejecutamos el comando sudo apt install postgresql-client para poder comunicarnos con el servidor.
    
- Una vez instalada la herramienta, repetimos el comando de conexión e ingresamos la contraseña postgres cuando el sistema nos la pidió.
    
- Ya dentro del monitor de la base de datos (pico=#), usamos el comando \dt para listar todas las tablas disponibles y así identificar dónde podría estar la información.
    
- Notamos que existía una tabla llamada flags, por lo que ejecutamos una consulta directa con el comando SELECT * FROM flags; para ver todo su contenido.
    
- El servidor nos devolvió una fila con los datos de esa tabla, donde venía escrita nuestra bandera
picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
### Notas
### Referencias