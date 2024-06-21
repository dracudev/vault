`typedef struct {` 
	`tipo field;` 
	`tipo field;` 
	`tipo field;` 
`} nombreStruc;` 

`typedef struct s_list {` 
	 `char nombre[50];` 
	 `int edad;` 
	 `float altura;` 
 `} t_list;` 

Por norma s_list (structure) y t_list(type) 
Después se declaran e inician como un tipo de variable normal: 
`Persona persona1;` 
`persona1 = {"Maria Lopez", 28, 1.65};` 

- -> se utiliza para acceder mediante puntero a los fields de una struct 
    - `Persona p` 
    - `p->nombre` 
    - `p->edad` 
- . Se utiliza para acceder directamente al valor de la variable de la struct.
    - `p.nombre` 
    - `p.edad`