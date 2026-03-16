### Piece by Piece
### Descripcion
After logging in, you will find multiple file parts in your home directory. These parts need to be combined and extracted to reveal the flag.
SSH to `dolphin-cove.picoctf.net`:`61272` and login as `ctf-player` with password `a15d25e1`.
### Solucion
- Se utilizó el comando `cat` para unir secuencialmente todos los fragmentos (`part_aa` a `part_ae`) en un solo archivo binario llamado `combined.zip`.
- Se empleó el comando `file` para confirmar que la unión fue exitosa y que el sistema reconocía el resultado como un archivo comprimido válido.
- Se ejecutó `unzip` sobre el archivo reconstruido, utilizando la contraseña "supersecret" para extraer el documento protegido.
- Se leyó el archivo extraído (`flag.txt`), revelando finalmente la bandera del desafío.
```
ctf-player@pico-chall$ ls
instructions.txt  part_aa  part_ab  part_ac  part_ad  part_ae
ctf-player@pico-chall$ cat instructions.txt
Hint:

- The flag is split into multiple parts as a zipped file.
- Use Linux commands to combine the parts into one file.
- The zip file is password protected. Use this "supersecret" password to extract the zip file.
- After unzipping, check the extracted text file for the flag.


ctf-player@pico-chall$ cat part_* > combined.zip
ctf-player@pico-chall$ file combined.zip
combined.zip: Zip archive data, at least v1.0 to extract
ctf-player@pico-chall$ unzip combined.zip
Archive:  combined.zip
[combined.zip] flag.txt password:
 extracting: flag.txt
ctf-player@pico-chall$ cat flag.txt
picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_da494d2e}
```
**picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_da494d2e}** 
### Notas
### Referencias