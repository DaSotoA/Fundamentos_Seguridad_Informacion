### SansAlpha
### Descripcion
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. 
`ssh -p 62490 ctf-player@mimas.picoctf.net`
Use password: `f3b61b38`
### Solucion
- Se establece conexión con la instancia del reto mediante SSH utilizando las credenciales y el puerto proporcionados en las instrucciones.
    
- Dado que no se pueden escribir letras, la estrategia consiste en obtener caracteres a partir de los mensajes de error del sistema. Se provoca un error intencional ejecutando un símbolo inválido (como `$`) y se guarda el texto resultante en una variable simbólica (como `_1`) mediante el uso de comillas invertidas (_backticks_) y la redirección de la salida de error (stderr) a la salida estándar (stdout):
    
    Bash
    
    ```
    _1=`$ 2>&1`
    ```
    
    _(Esta acción almacena la cadena `"bash: $: command not found"` dentro de la variable `_1`)._
    
- Se utilizan caracteres comodín (_wildcards_) para explorar el directorio actual y descubrir la ubicación del objetivo ejecutando `./*/*`. Esto revela que el archivo se encuentra en la ruta `./blargh/flag.txt`, lo cual se puede representar puramente con símbolos usando el patrón `./*/????.???`.
    
- Mediante la técnica de expansión de parámetros de Bash (_Bash parameter expansion_), se extraen caracteres individuales del mensaje de error previamente almacenado. Específicamente, la expresión `${_1:9:1}` extrae la letra "c", y `${_1:10:1}` extrae la letra "o".
    
- Se construye la ruta del comando `/bin/echo` combinando signos de interrogación (que actúan como comodín para sustituir exactamente un carácter) y las dos letras extraídas de la variable: `/???/?${_1:9:1}?${_1:10:1}` _(El intérprete evalúa esta cadena como `/???/?c?o`, la cual coincide en el sistema de archivos y se resuelve automáticamente como `/bin/echo`)._
    
- Finalmente, se combina el comando ensamblado con una sustitución de procesos para leer el contenido del archivo de la bandera sin escribir una sola letra de manera directa:
    
    Bash
    
    ```
    /???/?${_1:9:1}?${_1:10:1} "$(<./*/????.???)"
    ```
    
- Al ingresar esta instrucción simbólica, el sistema logra interpretar el comando, lee el archivo oculto y la consola imprime la bandera en pantalla.

picoCTF{7h15_mu171v3r53_15_m4dn355_640b6add}
### Notas
### Referencias
