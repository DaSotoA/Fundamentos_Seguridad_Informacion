### Safe Opener
### Descripcion
I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/83/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
Put the password you recover into the picoCTF flag format like:`picoCTF{password}`
### Solucion
- Se descarga y analiza el código fuente `SafeOpener.java`.
    
- Se localiza la función encargada de la validación de la contraseña (típicamente el método `openSafe` o similar).
    
- Se identifica que la contraseña no se almacena en texto plano, sino que el desarrollador la ha ofuscado utilizando el esquema de codificación Base64.
    
- Se extrae la cadena codificada (reconocible por el uso de caracteres alfanuméricos y frecuentemente terminada en el carácter de relleno `=`).
    
- Se utiliza una herramienta de decodificación Base64 para traducir la cadena a texto legible.
    
- El resultado de la decodificación revela directamente la bandera en su formato estándar.


**`picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}`**
### Notas
### Referencias