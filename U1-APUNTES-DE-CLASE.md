#  Graficación por Computadora: Repositorio de Apuntes Extendido
## **Unidad I: Introducción a la Graficación**

Este repositorio contiene una investigación exhaustiva sobre los cimientos de la computación gráfica, abarcando desde la evolución histórica hasta los algoritmos de bajo nivel para el procesamiento de imágenes.

---

##  Índice Detallado
1. [1.1 Historia y Evolución Detallada](#11-historia-y-evolución-detallada)
2. [1.2 Áreas de Aplicación Modernas](#12-áreas-de-aplicación-modernas)
3. [1.3 Fundamentos Matemáticos y Geométricos](#13-fundamentos-matemáticos-y-geométricos)
4. [1.4 Teoría y Modelos del Color](#14-teoría-y-modelos-del-color)
5. [1.5 Representación y Trazo de Primitivas](#15-representación-y-trazo-de-primitivas)
6. [1.6 Procesamiento Avanzado de Mapas de Bits](#16-procesamiento-avanzado-de-mapas-de-bits)
7. [ Bibliografía en Formato APA](#bibliografía)

---

##  1.1 Historia y Evolución Detallada

La graficación por computadora no es una disciplina aislada, sino el resultado de la convergencia entre el hardware de visualización y las matemáticas aplicadas.

* **La Era de los Pioneros (1950-1960):** * **Whirlwind (1951):** Fue la primera computadora que procesaba datos en tiempo real y los mostraba en un osciloscopio.
    * **SAGE (Semi-Automatic Ground Environment):** El primer sistema de control aéreo que utilizaba un lápiz óptico para interactuar con la pantalla.
* **La Consolidación Académica (1960-1970):** * **Ivan Sutherland (1963):** Desarrolló **Sketchpad**, estableciendo las bases de la interfaz gráfica de usuario (GUI) y el diseño asistido por computadora (CAD).
    * **Algoritmo de Línea de Bresenham (1965):** Un hito técnico que permitió optimizar el dibujo de líneas usando solo aritmética de enteros.
* **El Realismo y los Algoritmos de Sombreado (1970-1980):** * Aparición de los modelos de iluminación de **Gouraud (1971)** y **Phong (1975)**, que permitieron que los objetos poligonales parecieran curvos y suaves.
    * **Jim Blinn:** Introdujo el *Mapping* (texturizado) para añadir detalles superficiales sin aumentar la complejidad geométrica.
* **La Era de las GPU y el Ray Tracing (1990-Presente):** * Nacimiento de tarjetas aceleradoras como la **Nvidia GeForce 256** (1999).
    * Estandarización de APIs como **OpenGL** y **DirectX**.
    * Introducción del **Ray Tracing** en tiempo real, que simula el comportamiento físico de los fotones.



---

##  1.2 Áreas de Aplicación Modernas

La graficación ha permeado casi todos los aspectos de la vida digital contemporánea:

1.  **CAD/CAM (Computer-Aided Design/Manufacturing):** Vital en la ingeniería automotriz, aeroespacial y civil para prototipado virtual.
2.  **Visualización Científica y Médica:** Renderizado de volúmenes para tomografías axiales computarizadas (TAC) y simulaciones moleculares.
3.  **Realidad Extendida (XR):** Combinación de Realidad Virtual (VR), Aumentada (AR) y Mixta (MR) para entrenamiento industrial y telemedicina.
4.  **Cartografía Digital:** Procesamiento de nubes de puntos LiDAR para generar mapas 3D precisos de ciudades y terrenos.
5.  **Cine y Efectos Visuales (VFX):** Uso de motores de renderizado como *Arnold* o *RenderMan* para integrar elementos digitales con metraje real de forma indistinguible.

---

## 1.3 Aspectos Matemáticos de la Graficación

Para que un motor gráfico funcione, requiere una base matemática sólida basada en el Álgebra Lineal y la Geometría Analítica.

### Espacios de Coordenadas
Un objeto pasa por varias etapas antes de verse en pantalla:
1.  **Espacio de Objeto:** Coordenadas locales del modelo.
2.  **Espacio de Mundo:** Posición del objeto respecto a otros.
3.  **Espacio de Cámara (Vista):** Transformación según el punto de vista del observador.
4.  **Espacio de Proyección:** Conversión de 3D a un plano 2D (Perspectiva o de Proyección Paralela).

### Matrices de Transformación
Se utilizan matrices de $4 \times 4$ para manejar coordenadas homogéneas, permitiendo combinar traslación, rotación y escala en una sola operación:

$$T = \begin{bmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{bmatrix}$$
*Matriz de Traslación en 3D.*

---

## 1.4 Modelos del Color

El color en computación se define mediante modelos matemáticos que representan una parte del espectro visible.

* **Modelo RGB (Red, Green, Blue):** Basado en la síntesis aditiva. Es el estándar para monitores. Cada canal suele tener 8 bits de profundidad (0-255).
* **Modelo CMY/CMYK (Cyan, Magenta, Yellow, Key/Black):** Basado en la síntesis sustractiva para pigmentos e impresión.
* **Modelos HSV (Hue, Saturation, Value) y HSL (Lightness):** * **Hue (Matiz):** El color puro (0° a 360°).
    * **Saturation (Saturación):** La pureza del color.
    * **Value/Lightness:** La cantidad de luz. Estos modelos son preferidos en diseño por ser más intuitivos para el ojo humano.



[Image of RGB vs CMYK color models]


###  Tutorial: Iluminación de Caras en Blender
Para entender la interacción de la luz con la geometría:
1.  **Configuración de Escena:** Crea un cubo (`Shift + A` > Mesh > Cube).
2.  **Materiales Progresivos:** Entra al *Shader Editor*. Conecta un nodo *Noise Texture* al *Base Color* para ver cómo el color varía según las coordenadas.
3.  **Sombreado (Shading):** Cambia entre *Flat Shading* (caras planas visibles) y *Smooth Shading* (promediado de normales para una apariencia curva).
4.  **Tipos de Luces:**
    * **Point Light:** Emite luz en todas direcciones (como un foco).
    * **Sun Light:** Luz direccional infinita (ideal para sombras paralelas).
    * **Area Light:** Simula una ventana o caja de luz, generando sombras suaves (*Soft Shadows*).

<img width="1884" height="959" alt="Image" src="https://github.com/user-attachments/assets/62d12bef-0778-4566-9b0f-aba77710c799" />

<img width="1437" height="849" alt="Image" src="https://github.com/user-attachments/assets/5bafbb7c-01ba-4da2-b58e-e53fdcd8ffd2" />

---

##  1.5 Representación y Trazo de Líneas y Polígonos

El proceso de convertir una línea matemática en píxeles se llama **Rasterización**.

* **Algoritmo DDA:** Calcula los puntos intermedios basándose en la pendiente $m$. Requiere redondeo en cada paso, lo que lo hace lento para procesadores antiguos.
* **Algoritmo de Bresenham:** Utiliza una variable de decisión de error para determinar el píxel más cercano a la trayectoria ideal, evitando divisiones y números flotantes.
* **Polígonos:** Se representan como una secuencia de aristas. El algoritmo de *Scan-line fill* recorre la imagen de arriba abajo llenando los espacios entre aristas pares e impares.

###  1.5.1 Formatos de Imagen
| Formato | Compresión | Características Principales |
| :--- | :--- | :--- |
| **JPEG** | Con pérdida | Ideal para fotos; utiliza Transformada Discreta de Coseno. |
| **PNG** | Sin pérdida | Soporta canal Alfa (transparencia); excelente para web. |
| **TIFF** | Variable | Estándar en impresión profesional y fotografía de alta fidelidad. |
| **WebP** | Alta | Desarrollado por Google para sustituir JPEG y PNG con menor peso. |

###  Práctica de Dibujo: Polígono y Flor de la Vida
1.  **Polígono:** Implementación mediante un ciclo que calcula vértices usando $x = r \cdot \cos(i \cdot \frac{2\pi}{n})$.

<img width="530" height="342" alt="Image" src="https://github.com/user-attachments/assets/06f7feda-9ef8-4eec-ab83-34ba0864b6a0" />

<img width="419" height="458" alt="Image" src="https://github.com/user-attachments/assets/2388f982-dfe3-4d04-ab65-22b8e9e2c405" />

2.  **Flor de la Vida:** Un ejercicio de geometría sagrada donde se trazan 19 círculos completos y 36 arcos parciales, todos interconectados para demostrar la precisión del trazo circular y el manejo de centros de coordenadas.

<img width="811" height="433" alt="Image" src="https://github.com/user-attachments/assets/cb117cd1-4e6e-470e-b83c-735db54dea85" />

---

##  1.6 Procesamiento de Mapas de Bits

Un mapa de bits (Raster) es una matriz bidimensional de píxeles $f(x, y)$.

* **Brillo y Contraste:** Operación punto a punto: $g(x,y) = \alpha \cdot f(x,y) + \beta$.
* **Convolución (Kernels):** Una matriz pequeña que se desliza sobre la imagen para filtrar datos.
    * **Blur (Desenfoque):** Promedia los píxeles vecinos.
    * **Sobel/Prewitt:** Detecta bordes calculando el gradiente de intensidad.
* **Histograma:** Representación gráfica de la distribución de tonos, vital para la corrección de color y la ecualización.

---

## Bibliografía (APA)

* Hearn, D., & Baker, M. P. (2006). *Gráficos por computadora con OpenGL*. Pearson Educación.
* Hughes, J. F., Van Dam, A., McGuire, M., Sklar, D. F., Foley, J. D., Feiner, S. K., & Akeley, K. (2014). *Computer Graphics: Principles and Practice*. Addison-Wesley Professional.
* Shreiner, D., Sellers, G., Kessenich, J., & Licea-Kane, B. (2013). *OpenGL Programming Guide: The Official Guide to Learning OpenGL, Version 4.3*. Addison-Wesley.
* Blender Foundation. (2026). *Blender Documentation*. Recuperado de https://docs.blender.org/
* Scribbr. (2026). *Generador de Citas APA*. Recuperado de https://www.scribbr.es/citar/generador/

---
