### hashcrack
### Descripcion
A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server?Access the server using 
`nc verbal-sleep.picoctf.net 53154`
### Solucion
1. Se establece conexión con el servidor del reto ejecutando el comando proporcionado en la terminal: `nc verbal-sleep.picoctf.net 61932`
    
2. Al conectar, el servicio arroja un mensaje de bienvenida informando que se ha detectado una contraseña débil para el usuario "admin" y presenta en pantalla la cadena criptográfica (_hash_) correspondiente. Luego, deja la consola en pausa esperando que el usuario ingrese la contraseña en texto plano.
    
3. Se copia exactamente la cadena del _hash_ arrojada por la terminal.
    
4. Dado que el objetivo es romper un _hash_ débil (probablemente MD5 o SHA-1) correspondiente a una contraseña común, el enfoque más rápido es utilizar tablas precomputadas (_Rainbow Tables_) en lugar de realizar ataques de fuerza bruta locales que consumirían tiempo y recursos.
    
5. Se accede al servicio en línea especializado [CrackStation](https://crackstation.net/), el cual cuenta con bases de datos masivas de contraseñas ya procesadas en múltiples algoritmos.
    
6. Se pega el _hash_ copiado en la caja de búsqueda de CrackStation y se ejecuta la consulta.
    
7. La herramienta identifica la firma criptográfica y devuelve casi inmediatamente la contraseña original en texto plano.
    
8. Se regresa a la sesión activa de `netcat` en la terminal, se pega la contraseña recién descubierta y se presiona `Enter`.
    
9. Al autenticarse con éxito como administrador, el servidor valida el acceso y revela automáticamente el secreto oculto.
    

**Bandera:** `picoCTF{UseStr0nG_h@shEs_&PaSswDs!_eb2f8459}`
### Notas
**Herramientas utilizadas:** Terminal con utilidad `netcat` (o `nc`) y la plataforma de descifrado en línea `CrackStation`.
### Referencias
https://crackstation.net/