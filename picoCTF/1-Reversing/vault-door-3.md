### vault-door-3
### Descripcion
This vault uses for-loops and byte arrays.
The source code for this vault is here: [VaultDoor3.java](https://challenge-files.picoctf.net/c_fickle_tempest/224974a577c3aca738a0ca00a27b19754a1348d7b5cd8276501c762b6cf90251/VaultDoor3.java)
### Solucion
1. Se examina el bloque `checkPassword` en el código fuente de Java.
    
2. Se extrae la cadena de validación objetivo incrustada en el código.
    
3. Se realiza una traslación de la lógica de Java a Python, invirtiendo la dirección de las asignaciones de memoria para que la cadena objetivo retroceda por el algoritmo y recupere su forma original.
    
4. Al ejecutar el _script_ con los arreglos correctos, las permutaciones se deshacen y la contraseña se vuelve legible.
    
5. Se envuelve la cadena resultante en el formato estándar requerido por la plataforma.
    

**Bandera:** `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_120567}`
### Notas
### Referencias