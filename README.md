# Prácticas de Ecuaciones Diferenciales y Ecuaciones en Derivadas Parciales con Julia

Libro de prácticas con **ejercicios resueltos** de ecuaciones diferenciales ordinarias (EDO) y ecuaciones en derivadas parciales (EDP), implementados en el lenguaje [Julia](https://julialang.org). Está construido como un [libro Quarto](https://quarto.org) y sigue la estructura del proyecto de referencia [asalber/analisis-practicas-julia](https://github.com/asalber/analisis-practicas-julia).

La mayoría de los ejercicios son **aplicaciones a las ciencias, la ingeniería y las finanzas** (enfriamiento, epidemias, farmacocinética, circuitos, vibraciones, valoración de opciones, difusión, caos determinista, etc.).

## Contenidos

1. **EDO de primer orden** — campos de direcciones, líneas de fase, bifurcaciones; métodos separables, homogéneas, exactas, factores integrantes, lineales y Bernoulli.
2. **Geometría de un sistema de EDO** — campo vectorial, espacio y diagrama de fases, puntos de equilibrio.
3. **Sistemas de EDO lineales** — forma matricial, matriz exponencial, existencia y unicidad, diagramas de fases.
4. **Ecuaciones lineales de orden superior** — coeficientes constantes, resonancia, vibraciones.
5. **Sistemas de EDO no lineales** — linealización, ciclos límite, nulclinas, bifurcación de Hopf.
6. **Sistemas dinámicos discretos** — mapa logístico, diagramas de telaraña y de bifurcación, caos.
7. **EDP de primer orden** — advección, método de características, ondas de choque.
8. **EDP de segundo orden** — separación de variables, series de Fourier, calor, ondas y Laplace.
9. **Función de Green** — problemas de contorno, desarrollo espectral.
10. **Dependencia de los datos e introducción al caos** — atractor de Lorenz, exponentes de Lyapunov.
11. **Aplicaciones en Ciencias e Ingeniería** — problemas integradores (SIR, farmacocinética, aletas, opciones, mercados).

## Requisitos

- [Julia](https://julialang.org/downloads/) 1.11 o superior.
- [Quarto](https://quarto.org/docs/download/) 1.4 o superior.
- Los paquetes de Julia listados en `Project.toml` (véase más abajo).

Instalación de los paquetes de Julia:

```julia
using Pkg
Pkg.add(["SymPy", "Plots", "DifferentialEquations", "LinearAlgebra",
         "LaTeXStrings", "Roots", "NLsolve", "SpecialFunctions",
         "QuadGK", "Statistics"])
```

Para que Quarto ejecute los bloques de código de Julia se usa el motor de Jupyter con el kernel de Julia (`IJulia`):

```julia
using Pkg
Pkg.add("IJulia")
using IJulia
installkernel("Julia")
```

## Compilación

Desde la carpeta del proyecto:

```bash
# Vista previa con recarga automática
quarto preview

# Generar el sitio web (HTML) en la carpeta docs/
quarto render

# Generar solo un formato concreto
quarto render --to html
quarto render --to pdf
quarto render --to epub
```

El resultado se escribe en la carpeta `docs/`.

## Estructura del proyecto

```
edo-edp-practicas-julia/
├── _quarto.yml        # Configuración del libro (capítulos y formatos)
├── index.qmd          # Prefacio
├── 01-...qmd … 11-...qmd  # Capítulos con ejercicios resueltos
├── img/               # Imágenes
├── Project.toml       # Dependencias de Julia
└── README.md
```

## Estilo de los ejercicios

Cada ejercicio se presenta como un enunciado aplicado dividido en apartados. Cada apartado incluye:

- una **Ayuda** plegable con la idea o el método,
- una **Solución** plegable con el código de Julia y su interpretación.

Al final de cada capítulo se proponen ejercicios adicionales sin resolver.

## Licencia

Esta obra se distribuye bajo licencia [Creative Commons Reconocimiento-NoComercial-CompartirIgual 4.0 (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.es).
