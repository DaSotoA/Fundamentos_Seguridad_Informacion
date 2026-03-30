### RED
### Descripcion
RED, RED, RED, RED
Download the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)
### Solucion
1. Se descarga el archivo de imagen `red.png` a la máquina local o entorno de trabajo.
    
2. Sabiendo que es un archivo PNG y que el reto pertenece a la subcategoría de esteganografía forense, se opta por utilizar `zsteg`, una herramienta de línea de comandos especializada en detectar datos ocultos específicamente en imágenes PNG y BMP.
    
3. Se ejecuta el comando en la terminal utilizando el parámetro `-a` (para forzar un escaneo profundo de todos los métodos esteganográficos soportados): `zsteg -a red.png`
    
4. Al revisar los resultados arrojados por la herramienta, se identifica una cadena de texto sospechosa codificada en formato Base64: `cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==`
    
5. Se procede a decodificar dicha cadena utilizando una herramienta externa (como CyberChef) o directamente en la terminal mediante el comando nativo de Linux: `echo "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d`
    
6. El resultado de la decodificación revela el texto plano, mostrando la bandera final del desafío.

picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
### Notas
**Herramientas utilizadas:** Analizador esteganográfico (`zsteg`) y decodificador Base64 (`base64`).
### Referencias