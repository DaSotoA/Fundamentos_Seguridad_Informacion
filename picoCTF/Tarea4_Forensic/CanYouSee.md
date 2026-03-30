### CanYouSee
### Descripcion
How about some hide and seek?
Download this file [here](https://artifacts.picoctf.net/c_titan/5/unknown.zip).
### Solucion
- Se descarga y descomprime el archivo ZIP proporcionado en las instrucciones, obteniendo el archivo de imagen objetivo.
- Al visualizar la imagen de forma normal o intentar extraer texto plano básico (con comandos como `cat`), no se observa información relevante a simple vista.
- Se procede a realizar un análisis profundo utilizando una utilidad de extracción de metadatos, como `exiftool`, para examinar las propiedades internas del archivo directamente en la terminal: `exiftool ukn_reality.jpg`
- Al revisar meticulosamente la lista de propiedades devuelta por la herramienta, se identifica una anomalía: existe una cadena de texto sospechosa alojada en uno de los campos de atributos (como el _Attribution URL_). Dicha cadena se encuentra ofuscada bajo codificación Base64 (por ejemplo, `cGljb0NURntNRTc0RDQ3QV9ISUREM05fYjMyMDQwYjh9Cg==`).
- Se copia la cadena de texto identificada y se procede a decodificarla. Esto puede lograrse utilizando herramientas en línea (como CyberChef) o directamente mediante la terminal de Linux con el siguiente comando: `echo -n "cGljb0NURntNRTc0RDQ3QV9ISUREM05fYjMyMDQwYjh9Cg==" | base64 -d`
- El resultado de la decodificación revelará el texto en claro que contiene la bandera del reto.
picoCTF{ME74D47A_HIDD3N_4dabddcb}
### Notas
### Referencias