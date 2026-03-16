### Bookmarklet
### Descripcion
Why search for the flag when I can make a bookmarklet to print it for me?
Browse [here](http://titan.picoctf.net:56676/), and find the flag!
### Solucion
- Se inserta este codigo en la consola de inspeccion
```
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£Ö�ÓÚåÛÑ¢ÕÓ�Ó�Ç¡�¥Ìí";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
```

**picoCTF{p@g3_turn3r_0c0d211f}**
### Notas
### Referencias