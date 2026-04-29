### vault-door-training
### Descripcion
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility.
The source code for the training vault is here: [VaultDoorTraining.java](https://challenge-files.picoctf.net/c_fickle_tempest/644e8990318173b7dbdf06ac44bf700032ab93bd07e1bee168b32a0d882d2a8c/VaultDoorTraining.java)
### Solucion
1. Se descarga el archivo de código fuente `VaultDoorTraining.java` proporcionado en el reto.
    
2. Al examinar el archivo utilizando un editor de texto o el comando `cat` en la terminal, se observa la estructura básica de un programa en Java.
    
3. Se identifica el flujo principal del programa: solicita al usuario que ingrese una contraseña y luego extrae la subcadena que se encuentra dentro del formato `picoCTF{...}`.
    
4. Posteriormente, la cadena extraída se envía al método de validación llamado `checkPassword()`.
    
5. Al revisar el interior de la función `checkPassword()`, se descubre que la contraseña no está encriptada ni ofuscada; simplemente se compara utilizando el método `equals()` contra una cadena de texto en duro (_hardcoded_).
    
6. La cadena visible directamente en el código fuente es `w4rm1ng_Up_w1tH_jAv4_3808d338b46`.
    
7. Sabiendo que el programa espera este valor exacto sin las llaves para conceder el acceso, se deduce que la bandera completa consiste en envolver esa contraseña con el prefijo estándar.
    

**Bandera:** `picoCTF{w4rm1ng_Up_w1tH_jAv4_0009yrGMeEp}`
### Notas
**Herramientas utilizadas:** Cualquier editor de texto o comando de lectura en la terminal (`cat`, `less`, `grep`).
### Referencias