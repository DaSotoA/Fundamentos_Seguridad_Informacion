### shark on wire 2
### Descripcion
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/da02deeb6a0b3cd4fa866b6d1b30190e358240a2cd734c8da5d5a048f87fa038/capture.pcap). Recover the flag.
### Solucion
```
from scapy.all import *

packets = rdpcap('capture.pcap')
for p in packets:
    if UDP in p and p[UDP].dport == 5000:
        # Probemos restando 5000 al puerto de ORIGEN
        val = p[UDP].sport - 5000
        if 32 < val < 127:
            print(chr(val), end='')
print()
```

picoCTF{p1LLf3r3d_data_v1a_st3g0}
### Notas
No me funciono wireshark.
Asi que tuve que usar un programa en python.
### Referencias