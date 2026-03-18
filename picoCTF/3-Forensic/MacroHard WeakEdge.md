### MacroHard WeakEdge
### Descripcion
I've hidden a flag in this file. Can you find it?[Forensics_is_fun.pptm](https://challenge-files.picoctf.net/c_wily_courier/d78815176c19ddc85a1388233268d2f4c459fcbbaab197b4a29ebafc88294c54/Forensics_is_fun.pptm)
### Solucion
- **Verificación del archivo:** Se verificó el tipo de archivo, confirmando que se trata de un documento de PowerPoint:
```
   file "Forensics is fun.pptm"
```
- **Extracción de datos:** Se desempacó el documento utilizando `unzip`, dado que los archivos de Office son, en esencia, archivos comprimidos:
```
   unzip "Forensics is fun.pptm"
```
- **Búsqueda de anomalías:** Al extraer el contenido, se detectó la presencia de un archivo llamado `hidden`. Se navegó al directorio correspondiente y se mostró su contenido
```
   cd ppt/slideMasters
   cat hidden
```
- **Decodificación de la bandera:** Se observó que el archivo contenía una cadena en formato base64 con espacios. Se procedió a eliminar los espacios y decodificar la cadena para revelar la bandera:

```
   cat hidden | tr -d ' ' | base64 -d
```
### Notas
### Referencias