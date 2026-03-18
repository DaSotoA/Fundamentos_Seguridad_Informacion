### WebNet0
### Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key). 
Recover the flag.
### Solucion
┌──(kali㉿kali)-[~/webnet0]
└─$ wireshark capture.pcap 
- Se le agrega el key y se desencriptan los paquetes y se abren los TLS.
picoCTF{nongshim.shrimp.crackers}
### Notas
- TLS (Transport Layer Security) es el protocolo criptográfico estándar para asegurar comunicaciones en Internet, encriptando datos entre un navegador y un servidor. Sucesor de SSL, garantiza la privacidad, integridad y autenticación de la información, permitiendo conexiones HTTPS seguras.
### Referencias