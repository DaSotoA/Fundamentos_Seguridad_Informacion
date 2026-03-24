### HashingJobApp
### Descripcion
If you want to hash with the best, beat this test!`nc saturn.picoctf.net 60382`
### Solucion
1. Se establece conexión con el servidor especificado en las instrucciones utilizando Netcat. El comando ejecutado suele tener la estructura: `nc saturn.picoctf.net [puerto]`.
2. Una vez conectado, la terminal devuelve una cadena de texto aleatoria (por ejemplo, "my sixteenth birthday") y solicita su equivalente en formato MD5.
3. Se copia la cadena de texto mostrada y se calcula su hash MD5 utilizando una herramienta de línea de comandos (como `echo -n "texto" | md5sum` en sistemas Linux) o un generador en línea.
4. Se introduce el hash resultante en la terminal de Netcat y se envía.
5. Este ciclo de recibir el texto, generar el hash correspondiente y enviarlo se repite tres veces consecutivas.
6. Si los tres hashes introducidos son correctos y se procesan dentro del margen de tiempo, la consola imprime la bandera del reto.

**Bandera:** `picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}`
### Notas
### Referencias