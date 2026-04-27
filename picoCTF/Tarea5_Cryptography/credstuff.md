### credstuff
### Descripcion
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).
The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
### Solucion
1. Se descargan y descomprimen los archivos proporcionados por el reto. El archivo extraído típicamente contiene dos documentos de texto: `usernames.txt` y `passwords.txt`.
    
2. Para encontrar al objetivo, se busca el nombre `cultiris` dentro del archivo de usuarios. Utilizando utilidades de terminal como `grep -n "cultiris" usernames.txt` (o la función de búsqueda de un editor de texto), se identifica que este usuario se ubica exactamente en la **línea 378** del documento.
    
3. Sabiendo que los archivos mantienen una relación paralela (el usuario en la línea _X_ corresponde a la contraseña en la línea _X_), se procede a extraer el contenido de la línea 378 en el archivo de contraseñas.
    
4. La contraseña extraída es la cadena `cvpbPGS{P7e1S_54I35_71Z3}`.
    
5. Al analizar la sintaxis de la cadena, la longitud y la posición de las llaves sugieren que oculta el formato estándar `picoCTF{...}`. El prefijo `cvpbPGS` es la firma inconfundible de que el texto ha sido ofuscado utilizando el algoritmo **ROT13** (un Cifrado César con un desplazamiento exacto de 13 posiciones).
    
6. Se procede a decodificar la cadena aplicando ROT13. En este cifrado, la primera mitad del alfabeto se intercambia por la segunda, mientras que los números y caracteres especiales (como los guiones bajos y las llaves) permanecen intactos.
    
7. Al revertir el desplazamiento, el texto recupera su legibilidad y revela la bandera completa.
    

**Bandera:** `picoCTF{C7r1F_54V35_71M3}`
### Notas
**Herramientas utilizadas:** Comandos de procesamiento de texto en terminal (`grep`, `sed`, `awk` o `cat`) y una herramienta de decodificación ROT13 (puede ser CyberChef, un script de Python, o el comando `tr 'A-Za-z' 'N-ZA-Mn-za-m'` en bash).
### Referencias
