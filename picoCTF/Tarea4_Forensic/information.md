### information
### Descripcion
Files can always be changed in a secret way. Can you find the flag?
[cat.jpg](https://challenge-files.picoctf.net/c_wily_courier/76e95e3e6ee69b4f82b3cea25051f5a9a5918b57809a1f90b29b06b776c73bc7/cat.jpg)
### Solucion
- Se descarga el archivo `cat.jpg` proporcionado en el enunciado del reto.
- Como buena práctica inicial, se verifica la integridad del archivo utilizando comandos básicos de terminal como `file`, `hexdump` o `binwalk`. Esto confirma que efectivamente se trata de un formato de imagen JPG válido y no de un archivo diferente cuya extensión fue falsificada.
- Confirmada la validez de la imagen, el análisis se dirige hacia la inspección de sus metadatos (la información descriptiva incrustada en el archivo). Se puede utilizar cualquier visor de imágenes avanzado o herramientas específicas de terminal como `exiftool`.
- Al revisar minuciosamente las propiedades detalladas de la imagen, se detecta una anomalía evidente en el campo de la Licencia (_License_). En lugar de contener información de derechos de autor estándar, este campo alberga una cadena de texto ofuscada: `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`.
- Por la composición de sus caracteres y su terminación, se deduce que la cadena está codificada en formato Base64. Se copia el texto y se decodifica directamente en la terminal de Linux mediante la siguiente instrucción: `echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d`
- Al ejecutar la instrucción, la consola procesa la decodificación e imprime el texto en claro, revelando la bandera del reto.
picoCTF{the_m3tadata_1s_modified}
### Notas
### Referencias