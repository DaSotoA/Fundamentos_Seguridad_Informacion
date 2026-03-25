### Python Wrangling
### Descripcion
Python scripts are invoked kind of like programs in the Terminal...
Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/0af80634c4b5f2dc40a20b1e0808ddef0fb3b730764a045e7cd2f94910ba0c09/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/0af80634c4b5f2dc40a20b1e0808ddef0fb3b730764a045e7cd2f94910ba0c09/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/0af80634c4b5f2dc40a20b1e0808ddef0fb3b730764a045e7cd2f94910ba0c09/flag.txt.en)?
### Solucion
- Se descargan los tres archivos descritos en el enunciado del reto.
- Se ejecuta el _script_ `ende.py` en la terminal (por ejemplo, ingresando `python3 ende.py -h`) para revisar el manual de ayuda y entender su sintaxis. El programa imprimirá en pantalla que su modo de uso requiere un argumento que indique la operación (`-e` para cifrar o `-d` para descifrar), seguido del archivo objetivo.
- Para proceder a descifrar el documento de la bandera, se invoca el _script_ en la terminal utilizando el parámetro correspondiente y el nombre del archivo encriptado: `python3 ende.py -d flag.txt.en`
- Al ejecutar dicho comando, el programa pausará su ejecución y solicitará una contraseña para completar la acción. Se debe abrir el archivo `pw.txt`, copiar su contenido y pegarlo directamente en la terminal.
- Tras ingresar la contraseña correcta, el _script_ desencriptará el contenido del archivo y mostrará la bandera final en la pantalla.
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}
### Notas
### Referencias