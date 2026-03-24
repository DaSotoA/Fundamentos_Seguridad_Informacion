### Java Code Analysis!?!
### Descripcion
BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book! Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/480/bookshelf-pico.zip). Website can be accessed [here!](http://saturn.picoctf.net:65329/).
### Solucion
- Primero, iniciamos sesión en la página web del reto usando las credenciales básicas de user y user.
- Después, revisamos el código fuente que descargamos y descubrimos una falla de seguridad importante: el sistema usaba una contraseña secreta muy predecible y débil, literalmente 1234, para firmar y validar los tokens JWT.
- Abrimos las herramientas de desarrollador de nuestro navegador, buscamos la sección de Local Storage y copiamos nuestro token actual, el cual nos identificaba como un usuario normal con permisos limitados.
- Fuimos a la página de jwt.io y pegamos el token para editar su contenido. Ahí modificamos nuestros datos para que el sistema creyera que nuestro rol era Admin y nuestro ID de usuario era 2.
- En esa misma página, ingresamos la clave secreta 1234 en la sección de la firma criptográfica para sellar nuestro nuevo token y hacerlo pasar por uno totalmente legítimo.
- Regresamos a la página del reto, borramos el token viejo en el Local Storage, pegamos el nuevo que acabábamos de falsificar, actualizamos también el valor de token-payload y recargamos la página.
- Al actualizar, el servidor validó nuestro token falsificado usando su clave 1234, se lo creyó por completo y nos dio acceso total de administrador.
picoCTF{w34k_jwt_n0t_g00d_7745dc02}
### Notas
### Referencias
