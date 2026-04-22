### waves over lambda
### Descripcion
We made a lot of substitutions to encrypt this. 
Can you decrypt it?Connect with nc fickle-tempest.picoctf.net 50930.
### Solucion
- Se establece conexión con el servidor proporcionado a través de la terminal de Linux ejecutando el comando correspondiente (por ejemplo, `nc fickle-tempest.picoctf.net 50930`).
    
- El servidor responde con el siguiente texto inicial cifrado: `ubtksaym cwsw hm qbgs flak - fswpgwtuq_hm_u_bnws_lazvra_rau18625` Acompañado de un largo texto en la parte inferior que comienza con `dw dwsw tby zguc zbsw ycat a pgasyws...`
    
- Al inspeccionar el formato, se deduce que no es un Cifrado César o Vigenère estándar. La preservación de espacios y puntuación, junto con la provisión de un texto largo de apoyo, es el indicador clásico de que se está ante un Cifrado de Sustitución Simple (monoalfabético), diseñado específicamente para ser roto mediante análisis estadístico.
    
- Se procede a realizar un análisis de frecuencias de los caracteres. Esto implica contar qué letras se repiten más en el texto cifrado largo y compararlas con la distribución de frecuencias natural del idioma inglés (donde letras como la 'e', 't', 'a' y 'o' son las más comunes, y palabras de tres letras suelen ser 'the' o 'and').
    
- Este proceso iterativo de adivinanza de letras puede automatizarse utilizando solucionadores de criptogramas en línea (como _quipqiup_ o herramientas de dcode.fr) donde se introduce todo el texto proporcionado por el servidor.
    
- La herramienta estadística analiza la distribución, identifica que el texto largo corresponde a un pasaje de la novela _Robinson Crusoe_ y deduce el mapeo exacto del alfabeto.
    
- Al aplicar esta sustitución a la cadena inicial, el texto cifrado `ubtksaym cwsw hm qbgs flak` se revela como `congrats here is your flag`.
    
- Posteriormente, se decodifica la segunda parte de la cadena, obteniendo el texto en claro.

- El formato es diferente como lo indican las pistas, asi que se le quita la parte de picoCTF{}.

frequency_is_c_over_lambda_dac18625
### Notas
### Referencias