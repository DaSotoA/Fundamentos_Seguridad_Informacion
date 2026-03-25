### Specialer
### Descripcion
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. 
Please start an instance to test your very own copy of Specialer. `ssh -p 55446 ctf-player@saturn.picoctf.net`. The password is `fd7746b4`
### Solucion
- Se establece conexión con la instancia del servidor proporcionado para el reto, accediendo a la consola interactiva.
    
- Ante la ausencia del comando `ls`, se utiliza el comando interno `echo` junto con el comodín asterisco (`*`) para que el intérprete expanda y liste los elementos del directorio actual. Al ejecutar `echo *`, la consola devuelve los nombres de tres subdirectorios: `abra`, `ala` y `sim`.
    
- Para explorar qué hay dentro de esos subdirectorios, se amplía el comodín ejecutando `echo */*`. Esto revela la existencia de varios archivos de texto anidados, llamando la atención el archivo `ala/kazam.txt`.
    
- Dado que los comandos externos de lectura de texto están bloqueados, se recurre a una técnica de redirección de entrada nativa de Bash para extraer el texto. Se construye una instrucción combinando `echo` y la sustitución de comandos con la sintaxis `$(<ruta_del_archivo)`.
    
- Se ejecuta el comando completo utilizando la ruta absoluta del archivo objetivo: `echo "$(< /home/ctf-player/ala/kazam.txt)"`
    
- Al procesar la instrucción, la función interna de Bash lee directamente el contenido del archivo y lo imprime en la salida estándar, revelando la bandera.
picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_38f5cc78}
### Notas
### Referencias