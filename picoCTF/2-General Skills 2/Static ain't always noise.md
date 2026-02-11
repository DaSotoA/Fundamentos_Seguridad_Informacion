### Static ain't always noise
### Descripcion
Can you look at the data in this binary? The bash script might help![static](https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh)
### Solucion
- Usando chmod 
```
davidSoA-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static
--2026-02-11 14:34:55--  https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.95, 3.160.5.40, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16776 (16K) [application/octet-stream]
Saving to: 'static'

static                                                     100%[========================================================================================================================================>]  16.38K  --.-KB/s    in 0.006s  

2026-02-11 14:34:56 (2.76 MB/s) - 'static' saved [16776/16776]

davidSoA-picoctf@webshell:~$ ls
README.txt  big-zip-files  big-zip-files.zip  enc_flag  files  files.zip  static
davidSoA-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh
--2026-02-11 14:35:56--  https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.40, 3.160.5.18, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                                                   100%[========================================================================================================================================>]     785  --.-KB/s    in 0s      

2026-02-11 14:35:57 (269 MB/s) - 'ltdis.sh' saved [785/785]

davidSoA-picoctf@webshell:~$ chmod +x ltdis.sh 
davidSoA-picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
davidSoA-picoctf@webshell:~$ grep "picoCTF" static.ltdis.strings.txt 
   3020 picoCTF{d15a5m_t34s3r_20335e41}
```

picoCTF{d15a5m_t34s3r_20335e41}
### Notas
- La funcion chmod -x permíte ejecuta el archivo dado.
### Referencias
- https://www.freecodecamp.org/espanol/news/comando-chmod-como-cambiar-permisos-de-archivo-en-linux/