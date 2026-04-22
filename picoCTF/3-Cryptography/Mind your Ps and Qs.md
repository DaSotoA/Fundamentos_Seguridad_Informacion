### Mind your Ps and Qs
### Descripcion
In RSA, a small e value can be problematic, but what about N? Can you decrypt this?[values](https://challenge-files.picoctf.net/c_wily_courier/2bbb4086ce95d3e431695877b72b7ea062756cb58e97fb4b5a9f3b61ae21ce28/values)
### Solucion
1. Se descarga y abre el archivo de texto proporcionado (`values`), el cual contiene los números decimales para $c$, $n$ y $e$.
    
2. En la criptografía RSA, la seguridad depende de que el módulo $n$ (que es público) sea producto de dos números primos gigantescos ($p$ y $q$). Si $n$ es lo suficientemente pequeño, puede ser factorizado rápidamente.
    
3. Se toma el valor numérico de $n$ y se introduce en una base de datos de factorización en línea (como _FactorDB.com_) o se utiliza un _script_ matemático local. La herramienta descompone inmediatamente $n$ en sus dos factores primos originales, revelando los valores de $p$ y $q$.
    
4. Teniendo los primos expuestos, se procede a programar un breve _script_ en Python para derivar la llave privada ($d$):
    
    - Se calcula la función Totient de Euler: $\phi(n) = (p-1) \times (q-1)$.
        
    - Se calcula $d$ como el inverso modular de $e$ módulo $\phi(n)$ utilizando librerías matemáticas o la función nativa `pow(e, -1, phi_n)`.
        
5. Una vez obtenido $d$, se descifra el mensaje numérico elevando el texto cifrado a la llave privada módulo $n$: $m = c^d \pmod n$.
    
6. El resultado matemático ($m$) será un número decimal largo. Se convierte a formato hexadecimal y posteriormente se decodifica como caracteres de texto ASCII.
    
7. Al imprimir la cadena decodificada, se revela el texto en claro.
    

**Bandera:** `picoCTF{sma11_N_n0_g0od_1dc7ae91}`
### Notas
**Herramientas utilizadas:** Base de datos de factores (_FactorDB_), intérprete de Python, funciones de inverso modular y decodificación de bytes (`long_to_bytes` de la librería `Crypto.Util.number`).
### Referencias