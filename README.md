# tp0

Paso 0: Entorno de Trabajo

a. Capturas de pantalla de la ejecución del aplicativo (con y sin Valgrind).
![Ejecucion sin valgrind](https://github.com/Andivisciglio/tp0/img/Run_0.png)
![Ejecucion con valgrind](https://github.com/Andivisciglio/tp0/img/Valgrind_0.png)

b. ¿Para qué sirve ​ Valgrind​ ? ¿Cuáles son sus opciones más comunes?
Valgrind es una herramienta de debugeo que sirve para realizar seguimientos en el uso de la memoria por parte del programa que queremos ejecutar. Su opcion mas comun es Memcheck pero tambien cuenta con las siguientes herramientas; Massif, Cachegrind y Helgrind.
Memcheck, el mas utilizado, sirve particularmente para detectar leaks de memoria y accesos a memoria invalidos.

c. ¿Qué representa ​ sizeof()​ ? ¿Cuál sería el valor de salida de sizeof(char)​ y sizeof(int)​?

sizeof() nos indica la cantidad de bytes que ocupa en memoria el tipo recibido por parametro. Con respecto a las salidas de char e int, depende de la arquitectura que se este utilizando. Por ejemplo sizeof(int) me da un valor de 4 bytes mientras que sizeof(char) me da 1 byte ejecutado en una arquitectura de 64bits.


d. ¿El ​ sizeof()​ de una struct de C es igual a la suma del sizeof()​ de cada uno sus elementos? Justifique mediante un ejemplo.

No necesariamente. Puede ser el caso en el que si, pero el espacio en memoria que ocupa un struct depende no solo del tamanio de cada tipo de dato, sino que depende tambien del padding que se utilice.
Por ejemplo, si tengo un struct que solo tiene dos tipos int, entonces su sizeof() sera igual a la suma de los  sizeof() de sus elementos. Pero si tengo un struct con un char y un int, entonces el resultado del sizeof() puede ser mayor que al de la suma porque entra en juego el padding de memoria. Si se agrega la directiva __attribute__((packed)) al struct entonces podemos afirmar que siempre sera igual a la suma de los sizeof de sus miembros.


e. Investigar la existencia de los archivos estándar: STDIN, STDOUT, STDERR. Explicar brevemente su uso y cómo redirigirlos en caso de ser necesario (caracteres > ​ y ​ < ​ ) y como conectar la salida estándar de un proceso a la entrada estándar de otro con un pipe​ (carácter
|​ ).

Los archivos estandar STDIN, STDOUT, STDERR estan vinculados a la ejecucion de un programa y determinan distintos puntos de acceso para el mismo. Por ejemplo, el stdin es la entrada de texto hacia un programa y se puede redirigir con 'command < file'. El stdout es la salida del programa y se puede redireccionar utilizando 'command > file'. Stderr por su parte es donde se almacenan los mensajes de error y para redirigilo utilizamos 'command 2 > file'.
