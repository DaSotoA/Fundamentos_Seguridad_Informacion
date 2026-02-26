### GETaHEAD
### Descripcion
Find the flag being held on this server to get ahead of the competitionhttp://wily-courier.picoctf.net:57681/
### Solucion
- Se inspecciona la pagina en rojo, se reenvia el POST y se cambia a HEAD, se reenvia de nuevo y se busca la Flag
picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
- Con terminal
curl -s -I http://wily-courier.picoctf.net:57681/index.php
- 
### Notas

### Referencias