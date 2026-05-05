### Picker IV
### Descripcion
Can you figure out how this program works to get the flag?
Connect to the program with netcat:`$ nc saturn.picoctf.net 56747`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV.c). 
The binary can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV).
### Solucion
1. Se descarga el archivo ejecutable `picker-IV` al entorno local para su análisis estático.
    
2. Se emplean herramientas nativas de Linux para inspeccionar la tabla de símbolos del binario, ejecutando el comando `readelf -s picker-IV | grep win`.
    
3. El análisis revela que la función objetivo `win` se encuentra alojada en la dirección de memoria `40129e`.
    
4. Se establece una conexión con la instancia remota del reto a través de Netcat (`nc`).
    
5. Se ingresa la dirección de memoria `40129e` cuando el servidor solicita el _input_. El programa secuestra su propio flujo de control, salta a la dirección indicada y ejecuta el código que revela el secreto.
    

**Bandera:** `picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_01672a61}`
### Notas
Herramienta de análisis ELF (`readelf`) y cliente de conexión de red (`nc`).
### Referencias