### HideToSee
### Descripcion
How about some hide and seek heh?
Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).
### Solucion
1. Se descarga y analiza el archivo `atbash.jpg`. Al no existir texto cifrado visible a simple vista ni en los metadatos básicos, se infiere que los datos están incrustados en la estructura binaria de la imagen.
    
2. Se utiliza la herramienta de terminal `steghide`, especializada en ocultar y extraer datos dentro de archivos de imagen y audio. Se ejecuta el comando de extracción: `steghide extract -sf atbash.jpg`
    
3. Cuando la herramienta solicita una frase de contraseña (_passphrase_), se presiona `Enter` para dejarla en blanco. El programa extrae exitosamente un archivo de texto oculto llamado `encrypted.txt`.
    
4. Al visualizar el contenido de `encrypted.txt`, se revela la cadena cifrada asignada a esta instancia del reto: `krxlXGU{zgyzhs_xizxp_7142uwv9}`.
    
5. El nombre de la imagen original (`atbash.jpg`) funciona como una pista directa sobre el método de cifrado. El Cifrado Atbash es un cifrado de sustitución monoalfabético clásico en el que el alfabeto se invierte por completo (la A se convierte en Z, la B en Y, la C en X, etc.).
    
6. Se procede a descifrar la cadena aplicando el mapeo inverso del Atbash, respetando las mayúsculas, minúsculas y dejando intactos los símbolos (`{`, `}`, `_`) y los números (`7142`, `9`).
    
7. Al invertir el alfabeto, el texto cifrado recupera su legibilidad y revela el formato exacto de la plataforma.
    

**Bandera:** `picoCTF{atbash_crack_7142fde9}`
### Notas
**Herramientas utilizadas:** Utilidad de terminal `steghide` para la extracción de datos y un algoritmo de inversión de cadenas para el cifrado Atbash (implementable en Python o CyberChef).
### Referencias