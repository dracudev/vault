
1. Arriba del makefile definimos la variable: 
    1. OBJS = main.o calculadora.o 
2. La llamamos después:
    1. Programa: $(OBJS) 
3. Si ponemos @ delante de las instrucciones no se muestran en el terminal al hacer make 
    1. @echo $(OBJS): no se verá la instrucción echo 
4. **VARIABLE DE EXPASION SIMPLE** 
    1. OBJS := $(x) --> poniendo los dos puntos delante del igual indicamos que se tenga en cuenta el valor de x en ese mismo momento aunque se redefina en otro lugar después 
5. **VARIABLES COSTUMBRE** 
    1. CFLAGS = -Wall -Wextra -Werror 
    2. CC = gcc  
    3. LIB = ar rcs (Creación de la librería) 
    4. NAME = libft.a (Nombre del programa) 
    5. SRC = ft1.c ft2.c ft.3 (Elementos a compilar) 
    6. OBJ = $(SRC:.c=.o) --> El OBJ va a ser igual a los elementos de SRC compilados a .o     
    7. INCLUDE = libft.h (Incluir múltiples archivos) 
6. **VARIABLES AUTOMATICAS** 
	1. $< (Valor del primero de los elementos) 
	    1. Ej: compilando el programa $(OBJS) haría referencia al nombre main 
	2. $? (Valor de todos los elementos que se le pasen) 
	3. $@ (Valor del nombre de la regla) 
