`Objetivo: dependencias` 
	`instrucciones` 

`clean:` 
	`rm -f *.o` 

`all: $(NAME) --> programas que deben crearse SIOSI durante el make` 

**REGLAS IMPLICITAS** 

En compilación de archivos de tipo .c .o .out .a (…) makefile sabe cómo debe compilar y no hace falta indicar las instrucciones solo las dependencias. 

**RECOMPILACIÓN** 

Makefile recompila únicamente aquellos archivos cuya fecha de modificación se haya actualizado en relación al resto de dependencias. 

**PATRONES** 
- Operador % --> se reemplaza por otros caracteres 
    - %.o: %.c (A partir de cualquier archivo.c puedo generar archivo.o) 
    - Carpeta1/%.o: carpeta1/%.c (Podemos compilar por carpetas) 

Con \ escapamos los saltos de línea pudiendo seguir escribiendo en la siguiente línea.
