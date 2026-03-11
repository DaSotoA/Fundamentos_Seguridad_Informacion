### m00nwalk
### Descripcion
Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/f75cb0bb148301a92ee34a572e39d931d62c9c225f69e4b801ffa0fb6d2fe17b/message.wav) from the moon.
### Solucion
- Verificamos el tipo de archivo con file

`file message.wav` 

- Descargamos decodificador STTV de github y lo instalamos

> [https://github.com/colaclanth/sstv](https://github.com/colaclanth/sstv "https://github.com/colaclanth/sstv")

`cd /opt sudo git clone https://github.com/colaclanth/sstv cd sstv https://github.com/colaclanth/sstv`

- Decodificamos el mensaje oculto en el .wav y lo guardamos en flag.png

`sstv -d message.wav -o flag.png`

- Abrimos el archivo y copiamos la flag

`open flag.png`

picoCTF{beep_boop_im_in_space}
### Notas
### Referencias