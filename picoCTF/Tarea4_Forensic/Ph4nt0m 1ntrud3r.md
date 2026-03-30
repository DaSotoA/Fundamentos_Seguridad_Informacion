### Ph4nt0m 1ntrud3r
### Descripcion
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/bdda31c79c31975a5fe5402777bc87794655172e5d5bb2b569f1970df8efda34/myNetworkTraffic.pcap) and try to get the flag.
### Solucion
- Se descarga el archivo `myNetworkTraffic.pcap` y se procede a analizar su contenido. Esto puede realizarse mediante la interfaz gráfica de Wireshark o su contraparte de línea de comandos, `tshark`.
    
- Al ejecutar una lectura general (por ejemplo, con `tshark -r myNetworkTraffic.pcap`), se observa una cantidad inusual de sincronizaciones TCP (_TCP SYN_) dirigidas al puerto 80, así como múltiples retransmisiones de paquetes (_TCP Retransmission_), indicando un patrón sospechoso.
    
- Para buscar datos ocultos dentro de la estructura de estos paquetes, se inspecciona el contenido crudo en formato hexadecimal y ASCII utilizando el siguiente parámetro: `tshark -r myNetworkTraffic.pcap -x`
    
- Al examinar el volcado de memoria de las tramas de red, se detectan múltiples fragmentos de texto codificados en formato Base64 incrustados directamente en los paquetes.
    
- Se extraen manualmente estas cadenas Base64 y se decodifican (ya sea en la terminal o mediante herramientas como CyberChef). Al hacerlo, se obtienen las siguientes piezas en texto claro:
    
    - `cGljb0NURg==` -> `picoCTF`
        
    - `ezF0X3c0cw==` -> `{1t_w4s`
        
    - `bnRfdGg0dA==` -> `nt_th4t`
        
    - `XzM0c3lfdA==` -> `_34sy_t`
        
    - `YmhfNHJfZg==` -> `bh_4r_af`
        
    - `MzE4ZGIyMg==` -> `160980`
        
    - `fQ==` -> `}`
        
- Una vez recolectados todos los fragmentos decodificados, se ensamblan siguiendo el orden lógico de la oración para formar la estructura completa de la bandera.
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_af160980}
### Notas
### Referencias