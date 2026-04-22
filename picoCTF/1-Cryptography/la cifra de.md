### la cifra de
### Descripcion
I found this cipher in an old book.Can you figure out what it says? Connect with nc fickle-tempest.picoctf.net 53623.
### Solucion
- Se establece conexión con el servidor proporcionado utilizando la terminal de Linux (por ejemplo, `nc fickle-tempest.picoctf.net 53623` o la dirección específica de la instancia).
    
- El servidor devuelve un texto extenso que a simple vista parece estar cifrado mediante sustitución, pero manteniendo la puntuación y los espacios intactos.
    
- Se analiza el texto para identificar el algoritmo. El nombre del reto hace referencia histórica a "La cifra de Vigenère" (o cifra de Bellaso). Para confirmar esto, se puede introducir una muestra del texto en un analizador de cifrados automático (como el _Cipher Identifier_ de dcode.fr), el cual confirmará que se trata de un Cifrado Vigenère.
    
- Para romper el cifrado, se requiere la llave. Ya que el texto es lo suficientemente largo, se puede utilizar una herramienta de análisis de frecuencias o fuerza bruta (como el decodificador Vigenère de dcode.fr) para deducir la llave basándose en patrones del idioma inglés. La herramienta revela que la llave utilizada para cifrar el texto es la palabra `FLAG`.
    
- Se aplica la llave `FLAG` al texto cifrado completo (ya sea a través de la herramienta web o utilizando un _script_ automatizado en Python con aritmética modular).
    
- Al descifrar el mensaje, este se revela como un artículo histórico de Wikipedia en inglés sobre Giovan Battista Bellaso (el verdadero inventor del cifrado que hoy se le atribuye a Vigenère). Al final de todo el texto en claro, se encuentra incrustada la bandera del reto: **`picoCTF{b311a50_0r_v1gn3r3_c1ph3rb0896BFE}`**.

```
nc fickle-tempest.picoctf.net 53623 | python3 -c "import sys key = 'FLAG' k = 0 res = '' for c in sys.stdin.read(): if c.isalpha(): offset = 65 if c.isupper() else 97 res += chr((ord(c) - offset - (ord(key[k % 4]) - 65)) % 26 + offset) k += 1 else: res += c print(res)"
```
### Notas
**Herramientas utilizadas:** Cliente de conexión de red (`nc`), identificadores de cifrado y decodificadores Vigenère (como dcode.fr o _scripts_ en Python).
### Referencias
