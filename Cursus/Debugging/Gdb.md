1. Compilar el programa con –g para añadir información de depuración 
    1. gcc -g -o mi_programa mi_programa.c 
2. Ejecutar el programa con gdb 
    1. gdb a.out 
3. Iniciar el debug 
    1. (gdb) run -> nos muestra donde está el error 
    2. (gdb) bt -> seguimiento pila de llamadas