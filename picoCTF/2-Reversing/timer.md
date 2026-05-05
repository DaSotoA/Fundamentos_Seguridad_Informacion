### timer
### Descripcion
You will find the flag after analysing this apk
Download [here](https://artifacts.picoctf.net/c/449/timer.apk).
### Solucion
1. Se descarga el archivo `timer.apk` al entorno de trabajo.
    
2. Dado que un archivo APK es esencialmente un archivo comprimido, se utiliza la herramienta `unzip` para extraer todo su contenido y estructura de directorios originales.
    
3. Se ejecuta una búsqueda recursiva sobre los archivos extraídos utilizando `grep -r "picoCTF{"`.
    
4. El sistema identifica que la cadena objetivo se encuentra dentro de `classes3.dex`, uno de los archivos que contiene el código fuente compilado (Dalvik Executable) de la aplicación.
    
5. Debido a que es un archivo binario, se utiliza la herramienta `strings` para extraer únicamente el texto legible por humanos de dicho archivo, filtrando la salida nuevamente con `grep` para aislar la bandera.
    

**Bandera:** `picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}`
### Notas
Las aplicaciones móviles en Android no están encriptadas de forma predeterminada y su código fuente es fácilmente accesible. Este reto demuestra una mala práctica de seguridad crítica: empaquetar credenciales, banderas o secretos directamente dentro de los binarios del lado del cliente (`.dex`), ya que cualquier usuario puede deconstruir el instalador y extraer la información en minutos sin necesidad de ejecutar la aplicación.
### Referencias