### vault-door-5
### Descripcion
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding!
The source code for this vault is here: [VaultDoor5.java](https://challenge-files.picoctf.net/c_fickle_tempest/f2e90d844f6e64092bc1a611c16d52a832e0f2cb856991bc9fa205bcd0cd31bd/VaultDoor5.java)
### Solucion
1. Se analiza el archivo fuente `VaultDoor5.java` y se ubica el método `checkPassword()`.
    
2. Se identifica la cadena ofuscada que el programa espera, almacenada típicamente al final de la función de validación (dentro del método `equals()`).
    
3. Para obtener la contraseña original, se debe revertir el flujo de validación. Debido a que el programa original primero aplica _URL Encoding_ y luego _Base64_, la reversión requiere el orden inverso:
    
    - Primero, decodificar la cadena extraída desde Base64.
        
    - Segundo, decodificar el resultado utilizando _URL Decode_.
        
4. Se desarrolla un _script_ automatizado que extrae la cadena directamente del código fuente y aplica ambas decodificaciones de forma secuencial.
    
5. Al procesar las capas, el texto recupera su formato legible y se envuelve en la estructura estándar de la plataforma.
    

**Bandera:** `picoCTF{c0nv3rt1ng_fr0m_ba5e_64_4bb22721}`
### Notas
**Herramientas utilizadas:** Intérprete de Python con las librerías `base64` y `urllib.parse`.
### Referencias
