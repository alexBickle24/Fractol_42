¡Claro! Aquí tienes el archivo README.md en formato Markdown para tu proyecto.

Proyecto fract-ol 🎨💻
Este proyecto, llamado fract-ol, es una implementación en C de un generador de fractales, específicamente de los conjuntos de Mandelbrot y Julia, utilizando la librería gráfica MiniLibX. Este programa permite al usuario explorar estos fascinantes objetos matemáticos, permitiendo interactuar con ellos a través de funciones de zoom y movimiento.

¿Qué es un fractal?
Un fractal es un objeto geométrico cuya estructura básica, fragmentada o irregular, se repite a diferentes escalas. Esta propiedad se conoce como autosimilitud. Un ejemplo clásico es un copo de nieve que, al hacerle zoom, revela subestructuras que se asemejan al todo. Los fractales se generan mediante procesos iterativos, donde una regla simple se aplica una y otra vez para producir una complejidad infinita. Se encuentran en la naturaleza (nubes, líneas costeras, copos de nieve) y tienen aplicaciones en campos como las ciencias de la computación, la física y el arte.

El Conjunto de Mandelbrot y el Conjunto de Julia
El Conjunto de Mandelbrot es un fractal icónico definido en el plano complejo. Se construye a partir de la fórmula iterativa z_n+1=z_n 
2
 +c, donde c es un número complejo que representa un punto en el plano y z_0=0. Un punto c pertenece al conjunto de Mandelbrot si la secuencia de puntos z_n no se escapa al infinito. En nuestro programa, los puntos que escapan se colorean según la velocidad con la que lo hacen, creando los patrones visuales que caracterizan al fractal.

El Conjunto de Julia es una familia de fractales estrechamente relacionados con el Conjunto de Mandelbrot. Se utiliza la misma fórmula, z_n+1=z_n 
2
 +c, pero con una diferencia clave: z es un punto variable en el plano, y c es una constante elegida al inicio. Cada valor constante de c produce un conjunto de Julia diferente. Al igual que con el Conjunto de Mandelbrot, los puntos que no divergen al infinito forman el conjunto. El programa permite al usuario pasar los valores de la constante c como argumentos al iniciar el programa.

Tecnologías y Estructura del Código 🛠️
Este proyecto está escrito en C y se compila utilizando GNU Make. La visualización gráfica se maneja con la librería MiniLibX, una interfaz de programación de aplicaciones (API) simple para el entorno gráfico X-Window (utilizada en sistemas Unix/Linux) y macOS.

Archivos Clave del Proyecto:
main.c: Contiene la función principal main que maneja la validación de argumentos, la inicialización del entorno MiniLibX y el inicio del bucle principal del programa.

fractol.h: El archivo de cabecera principal. Define las estructuras de datos (t_image_data, t_mlx_enviroment, t_complex_factors) y las constantes (WIDTH, HEIGHT, MAND_MAX_X, etc.) utilizadas en todo el proyecto. También contiene los prototipos de todas las funciones.

render.c: Contiene las funciones principales de renderizado. La función render_set itera sobre cada píxel de la ventana y llama a la función de cálculo del conjunto correspondiente.

create_cgi_env.c: Se encarga de la configuración inicial del programa. La función select_set_to_render determina qué fractal se renderizará basándose en los argumentos de la línea de comandos, mientras que setup_mlx_enviroment inicializa la ventana y la imagen de MiniLibX.

color_treatment.c: Maneja la paleta de colores para los fractales. La función get_color_from_palethe devuelve un color basado en el número de iteraciones necesarias para que un punto se escape.

math_utils.c: Incluye funciones matemáticas auxiliares como ft_power_of para calcular potencias, las cuales son necesarias para las iteraciones de los conjuntos.

utils.c: Contiene funciones de utilidad genéricas. Destaca ft_atodbl, que convierte una cadena de caracteres a un número de punto flotante de doble precisión, utilizada para leer los factores de Julia desde la línea de comandos.

Características y Funcionalidad ✨
Exploración de Fractales: Permite la visualización y exploración de los conjuntos de Mandelbrot y Julia.

Interactividad: El usuario puede interactuar con el fractal usando el teclado y el ratón para:

Zoom: Acercar y alejar la vista para revelar la autosimilitud infinita del fractal.

Movimiento: Desplazarse por el plano para explorar diferentes regiones.

Parámetros Personalizables: Para el Conjunto de Julia, se pueden especificar los factores real e imaginario a través de argumentos de la línea de comandos, lo que permite la exploración de diferentes conjuntos.

Uso 🚀
Para compilar el programa, utiliza el siguiente comando:

Bash

make
Para ejecutar el programa y visualizar el Conjunto de Mandelbrot, usa:

Bash

./fractol Mandelbrot
Para visualizar un Conjunto de Julia con parámetros específicos:

Bash

./fractol Julia [factor_real] [factor_imaginario]
Por ejemplo:

Bash

./fractol Julia -0.8 0.156
