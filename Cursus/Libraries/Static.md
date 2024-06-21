- Debes compilar tu biblioteca estática libft.a utilizando los archivos fuente (*.c) que contienen las implementaciones de tus funciones. Esto se hace por separado utilizando un Makefile o comandos de compilación como gcc -c para compilar cada archivo fuente en un archivo objeto (*.o). 
    
- Luego, combinas estos archivos objeto en la biblioteca estática utilizando el comando                 
	- **ar rcs libft.a *.o.** 
    - ar: comando crear librería 
        - -c crear si no existe 
        - -r insertar files.o 
        - -s indexar la librería 
- Los programas de prueba o programas principales que utilizan tu biblioteca (libft.a) deben incluir los archivos de cabecera (libft.h) donde se declaran los prototipos de las funciones de la biblioteca. 
- Los programas deben ser compilados separadamente utilizando gcc u otro compilador, pero en el proceso de compilación, debes enlazar tu biblioteca estática libft.a junto con tus programas. Esto se hace pasando -L para especificar la ubicación de la biblioteca y -l<nombre> para indicar el nombre de la biblioteca (en este caso -lft para libft.a). 
- Por ejemplo, si tienes un archivo de prueba main.c que usa funciones de libft.a, el proceso de compilación podría verse así:
    - **gcc -o main main.c -L. -lft -I.** 
    - Debe estar el main, libft.a y libft.h en el directorio 
    - gcc (compila) -o (en .o) main (con el nombre "main") main.c (el archivo main.c) -L. (la librería está en el directorio actual) -lft (la librería se llama lib_ft) -I. (el header/includes está en el directorio actual) 

**#ifndef, #define y #endif** 

Estas directivas se utilizan juntas para evitar que un archivo de encabezado sea incluido más de una vez en el mismo archivo fuente, lo cual puede causar problemas como redefiniciones de tipos y variables. Este método se conoce como guardas de inclusión (inclusion guards) o inclusion guard macros. 

- #ifndef: Verifica si un identificador específico no ha sido definido previamente. 
    
- #define: Define el identificador especificado si no ha sido definido previamente. 
    
- #endif: Termina el bloque condicional iniciado por #ifndef.