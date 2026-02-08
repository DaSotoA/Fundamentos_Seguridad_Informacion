### plumbing
### Descripcion
- Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Additional details will be available after launching your challenge instance.
- Connect to fickle-tempest.picoctf.net 61737.
### Solucion
- Investigando hacerca de tuberias en netcat, se representan con un '|', esto se aplica con el comando nc (link) (puerto) | grep pico.
```
- dacid@LAPTOP-8H74K3S8:~$ nc fickle-tempest.picoctf.net 61737 | grep pico
picoCTF{digital_plumb3r_11fffFE5}
```

picoCTF{digital_plumb3r_11fffFE5}

### Notas
- el comando grep lo que hace es filtrar la informacion y buscar lo que contenga la palabra o contenido que le pongas despues, en este caso fue pico.
### Referencias
- https://gemini.google.com/app/76ef49a91caf257a?hl=es 1. ```
    nc fickle-tempest.picoctf.net 61737 | grep pico
    ```
    

**¿Qué hace este comando?**

- `nc fickle-tempest.picoctf.net 61737`: Se conecta al servidor, el cual empezará a escupir muchísimo texto (basura) muy rápido.
    
- `|` (El "pipe" o tubería): Toma todo ese texto basura y, en lugar de mostrártelo en pantalla, se lo pasa al siguiente comando.
    
- `grep pico`: Recibe el texto y **filtra** todo, mostrando _únicamente_ la línea que contenga la palabra "pico" (que es el formato de la bandera).
  

