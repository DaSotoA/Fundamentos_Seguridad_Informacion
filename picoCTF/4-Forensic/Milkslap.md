### Milkslap
### Descripcion
🥛http://wily-courier.picoctf.net:58480/
### Solucion
1. Al acceder al enlace, se muestra una página interactiva donde al mover el cursor se anima una imagen (dando una bofetada con leche a la persona). No hay un enlace directo de descarga a simple vista.
2. Se debe inspeccionar el código fuente de la página o simplemente abrir la imagen en una pestaña nueva y descargar el archivo de imagen base, el cual está en formato `.png`.
3. Al tratarse de un archivo PNG, se pueden emplear herramientas de esteganografía para buscar información oculta. Para este formato en particular, la herramienta ideal es `zsteg`.
4. Ejecutando el comando `zsteg nombre_de_la_imagen.png` en la terminal, la herramienta extrae los datos ocultos dentro de la imagen.
5. Entre los resultados que arroja `zsteg`, se encuentra la bandera en texto plano.

`picoCTF{imag3_m4n1pul4t10n_sl4p5}`
### Notas
**Herramientas utilizadas:** `zsteg`. Es una excelente herramienta de línea de comandos en entornos de ciberseguridad para detectar y extraer datos ocultos específicamente en archivos PNG y BMP (a diferencia de `steghide`, que suele utilizarse para JPG).
### Referencias