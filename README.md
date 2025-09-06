# fract-ol 🎨💻

**fract-ol** es un proyecto en **C** que implementa un generador de fractales, específicamente los conjuntos de **Mandelbrot** y **Julia**, utilizando la librería gráfica **MiniLibX**.  
El programa permite explorar estos fascinantes objetos matemáticos con **interactividad mediante zoom, movimiento y parámetros personalizables**.

---

## 🌌 ¿Qué es un fractal?
Un **fractal** es un objeto geométrico cuya estructura básica se repite a diferentes escalas, propiedad conocida como **autosimilitud**.  
Se generan mediante procesos iterativos donde una regla simple se aplica una y otra vez, produciendo una complejidad infinita.  

Ejemplos en la naturaleza: nubes, copos de nieve, líneas costeras.  
Aplicaciones: computación, física, arte y modelado de la naturaleza.

---

## 🔬 Mandelbrot y Julia
- **Conjunto de Mandelbrot**: definido en el plano complejo con la iteración  
  *z<sub>n+1</sub> = z<sub>n</sub>² + c*, con z₀ = 0.  
  Un punto pertenece al conjunto si no diverge al infinito.  
  Los colores dependen de la velocidad de escape del punto.

- **Conjunto de Julia**: usa la misma fórmula, pero con *c* como constante fija y *z* como variable.  
  Cada valor de *c* genera un fractal distinto.  
  El programa permite pasar *c* como argumento al ejecutarse.

---

## 🛠️ Tecnologías y Estructura del Código
- Lenguaje: **C**
- Librerías: **MiniLibX**
- Compilación: **GNU Make**

### Archivos principales
- **`main.c`** → función `main`, validación de argumentos, inicialización MiniLibX.  
- **`fractol.h`** → estructuras, constantes y prototipos globales.  
- **`render.c`** → funciones de renderizado y cálculo de fractales.  
- **`create_cgi_env.c`** → selección de fractal y setup del entorno gráfico.  
- **`color_treatment.c`** → paleta de colores y asignación por iteraciones.  
- **`math_utils.c`** → utilidades matemáticas (ej: `ft_power_of`).  
- **`utils.c`** → utilidades varias (ej: `ft_atodbl` para lectura de parámetros).  

---

## ✨ Características
- **Exploración interactiva** de Mandelbrot y Julia.  
- **Zoom** con ratón/teclado para profundizar en la autosimilitud infinita.  
- **Movimiento** para explorar diferentes regiones.  
- **Parámetros personalizables** para Julia (parte real e imaginaria de *c*).  

---

## 🚀 Uso
# Run Mandelbrot
./fractol Mandelbrot

# Run Julia with custom parameters
./fractol Julia [real] [imaginary]

# Example
./fractol Julia -0.8 0.156

### 🔧 Compilación

```bash
make
