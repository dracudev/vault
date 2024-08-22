- mlx_init(): iniciar libreria
- mlx_new_window(mlx, widht, weigth name): iniciar una ventana
- mlx_loop(mlx): renderizar
- mlx_new_image(mlx, width, weigth): crear una nueva imagen
- mlx_get_data_addr(img, bits_per_pixel, line_length, endian): pasamos la referencia de los bits, length y endian para que la libreria ajuste automaticaamente la direccion actual
- ft_mlx_pixel_put(img, x, y, color): pintar pixeles en la imagen. El color se escribe en representacion hexadecimal.
- mlx_put_image_to_window(mlx, window, img, x, y): printar un pixel de la imagen en la pantalla
```c
#include <mlx.h>

typedef struct	s_data {
	void	*img;
	char	*addr;
	int		bits_per_pixel;
	int		line_length;
	int		endian;
}				t_data;

int	main(void)
{
	void	*mlx;
	void	*mlx_win;
	t_data	img;

	mlx = mlx_init();
	mlx_win = mlx_new_window(mlx, 1920, 1080, "Hello world!");
	img.img = mlx_new_image(mlx, 1920, 1080);
	img.addr = mlx_get_data_addr(img.img, &img.bits_per_pixel, &img.line_length,
								&img.endian);
	my_mlx_pixel_put(&img, 5, 5, 0x00FF0000);
	mlx_put_image_to_window(mlx, mlx_win, img.img, 0, 0);
	mlx_loop(mlx);
}
```