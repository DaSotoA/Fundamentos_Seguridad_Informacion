### Serpentine
### Descripcion
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/36/serpentine.py)
### Solucion
- Se agrega print_flag() ya que al autor se le "olvido" la funcion para dar la bandera.
```
elif choice == 'b':
      print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
      print_flag()      
```

```
davidSoA-picoctf@webshell:~$ nano serpentine.py 
davidSoA-picoctf@webshell:~$ python serpentine.py 

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!


picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
a) Print encouragement
b) Print flag
c) Quit

```

picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
### Notas
### Referencias