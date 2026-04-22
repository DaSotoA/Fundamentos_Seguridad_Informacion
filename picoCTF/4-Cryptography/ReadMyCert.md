### ReadMyCert
### Descripcion
How about we take you on an adventure on exploring certificate signing requests.
Take a look at this CSR file [here](https://artifacts.picoctf.net/c/426/readmycert.csr).
### Solucion
1. Se descarga y analiza el archivo `readmycert.csr` dentro del entorno de trabajo.
    
2. Al ejecutar el comando `file readmycert.csr`, el sistema confirma que se trata de un archivo de solicitud de certificado en formato PEM.
    
3. Al visualizar el contenido crudo del archivo (por ejemplo, mediante `cat readmycert.csr`), se observa un bloque de texto codificado en Base64 encapsulado entre las cabeceras `-----BEGIN CERTIFICATE REQUEST-----` y `-----END CERTIFICATE REQUEST-----`. Este texto es ilegible a simple vista.
    
4. Para decodificar e inspeccionar los atributos internos de la solicitud, se recurre a `OpenSSL`, una robusta herramienta de línea de comandos estándar en entornos tipo UNIX para operaciones criptográficas.
    
5. Se ejecuta el comando de lectura de certificados: `openssl req -in readmycert.csr -noout -text`
    
6. Esta instrucción analiza la estructura matemática del archivo e imprime un desglose legible por humanos que incluye el algoritmo de la llave pública, la longitud de la firma y los datos de identidad.
    
7. Al inspeccionar la sección de "Asunto" (_Subject_), se identifica el campo `CN` (_Common Name_ o Nombre Común), el cual tradicionalmente alberga el dominio web a certificar.
    
8. En este caso, la inspección revela que el campo `CN` contiene directamente la cadena de texto con la bandera asignada a esta instancia del reto.
    

**Bandera:** `picoCTF{read_mycert_41d1c74c}`
### Notas
**Herramientas utilizadas:** Utilidad de terminal `OpenSSL` (específicamente el subcomando `req`).
### Referencias