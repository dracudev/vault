- Utilizamos **unsigned char** para trabajar con bytes ya que en la mayoría de sistemas un char equivale a un byte. 
- **Solapamiento** (memmove): ocurre cuando source es menor que dest, empezando a copiar en posiciones de memoria equivocadas y provocando perdidas de información. Para evitar esto comenzamos a copiar desde el final.  
- **Malloc** señala la cantidad de bytes del espacio que quiere reservarse mientras que calloc indica la cantidad de elementos deseados y el tamaño en bytes de cada elemento (sizeof). Además calloc inicializa todos los bits de espacio reservado a cero.  
    - Ambos devuelven la dirección inicial del espacio reservado 
    - Se debe liberar el espacio explícitamente una vez dejemos de trabajar con él con free(x). 
    - **Realloc** redimensiona un vector conservando sus valores. Se utiliza con vectores previamente inicializados con malloc. 
    - `Var = (typecasting *)malloc(len * sizeof(type));`
        - En *strings sumar 1 ('\0') al len 
    - BUENA PRÁCTICA: `if (var == NULL) { return (NULL) }` 


