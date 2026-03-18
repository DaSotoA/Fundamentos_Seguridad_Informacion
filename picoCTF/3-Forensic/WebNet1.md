### WebNet1
### Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key). Recover the flag.
### Solucion
- El paquete 47 se exportan los objetos http, y extraemos lo que sale en la linea 91 el cual es una imagen al momento de darle strings nos da la bandera.
- Todo con wireshark.
┌──(kali㉿kali)-[~/webnet0/webnet1]
└─$ open vulture.jpg 
                                                                             
┌──(kali㉿kali)-[~/webnet0/webnet1]
└─$ strings vulture.jpg                                   
JFIF
Exif
picoCTF{honey.roasted.peanuts}
### Notas
### Referencias