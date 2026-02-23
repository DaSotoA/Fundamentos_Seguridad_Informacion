### picobrowser
### Descripcion
This website can be rendered only by picobrowser, go and catch the flag!http://fickle-tempest.picoctf.net:60161
### Solucion
- Descargando user agent cambiando el browser.
`picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}`
- Con consola: curl https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser" | grep pico
### Notas
- User agent te puede ayudar a pasar por cualquier tipo de navegador.
### Referencias
- https://webextension.org/listing/useragent-switcher.html?version=0.6.6&type=install