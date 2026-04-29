### vault-door-1
### Descripcion
This vault uses some complicated arrays! I hope you can make sense of it, special agent. 
The source code for this vault is here: [VaultDoor1.java](https://challenge-files.picoctf.net/c_fickle_tempest/1f6a13a5b4d68ad4d70cb7feb13e64dfcad8b537b2e24c74f131bedb9b8883a7/VaultDoor1.java)
### Solucion
1. Se descarga y abre el archivo de código fuente `VaultDoor1.java`.
    
2. Al examinar el método `checkPassword()`, se observa que primero valida que la longitud de la contraseña sea exactamente de 32 caracteres.
    
3. Posteriormente, se presenta un bloque masivo de condicionales conectadas por el operador lógico `&&` (AND). Cada línea comprueba que un índice específico de la cadena de entrada corresponda a un carácter en particular. Por ejemplo:
    
    - `password.charAt(0) == 'd'`
        
    - `password.charAt(29) == 'a'`
        
    - `password.charAt(4) == 'r'`
        
4. Para resolverlo, existen dos enfoques:
    
    - **Enfoque Manual (Vieja Escuela):** Leer línea por línea e ir escribiendo los caracteres en un papel o documento de texto en el orden numérico correcto (del 0 al 31) para ensamblar el rompecabezas.
        
    - **Enfoque Programático:** Utilizar herramientas de línea de comandos en la terminal (`grep`, `awk`, `sort`) para extraer los números y las letras, ordenarlos numéricamente y concatenar la cadena completa en cuestión de milisegundos.
        
5. Una vez que se acomodan los 32 caracteres en sus índices correspondientes (0 a 31), se forma la cadena `d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4`.
    
6. Finalmente, se envuelve esta cadena en el formato estándar para validar la bandera.
    

**Bandera:** `picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_d52565}`
### Notas

### Referencias