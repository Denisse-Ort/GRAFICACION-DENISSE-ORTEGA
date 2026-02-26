#  Proyecto Integrador
## **Unidad I: Fundamentos y Aplicaciones de la Graficación por Computadora**

Este repositorio documenta el proceso de investigación, diseño y ejecución del Proyecto Integrador de la Unidad I. El enfoque central es la transición de geometrías euclidianas simples hacia entornos procedurales complejos con animación de cámara.



##  1. INICIO: Marco Conceptual y Propósito

### 1.1 Introducción a la Generación Procedural
La generación procedural es una técnica donde los datos se crean algorítmicamente en lugar de manualmente. En este proyecto, se utiliza para construir un escenario arquitectónico que responde a parámetros definidos en un script de Python, permitiendo una escalabilidad infinita y una precisión geométrica que sería difícil de alcanzar mediante modelado tradicional por vértices.

### 1.2 Justificación del Proyecto
El proyecto aborda la necesidad de comprender cómo la computadora interpreta las instrucciones de alto nivel para convertirlas en primitivas gráficas. Se seleccionó un diseño de pasillo curvo con giro a la izquierda para elevar la dificultad técnica, integrando:
* **Control de flujo (Ciclos):** Para la instanciación masiva de objetos.
* **Lógica Condicional:** Para la alternancia de materiales y transformaciones de escala.
* **Dinámica de Cámara:** Para explorar el espacio desde un ángulo de visión (FOV) específico.

### 1.3 Conceptos Matemáticos Fundamentales
Para que el escenario se manifieste correctamente, el script gestiona:
1. **Sistemas de Coordenadas:** Transformación de coordenadas locales a globales.
2. **Traslación Afín:** Desplazamiento de los cubos en los ejes X e Y para generar la curvatura.
3. **Normales de Superficie:** Cruciales para que la luz del punto (`POINT LIGHT`) interactúe de forma realista con las caras de las paredes.



##  2. DESARROLLO: Análisis de la Implementación

En esta fase se desglosan los componentes técnicos del proyecto, los cuales serán respaldados por capturas de pantalla del entorno de desarrollo.

### 2.1 Gestión de Materiales y Teoría del Color (RGB)
Se implementó el modelo de color **RGB**, asignando valores normalizados en el rango $[0, 1]$. 
* **ParedOscura (0.1, 0.1, 0.1):** Representa un valor de baja luminancia, diseñado para absorber la luz y resaltar las sombras arrojadas.
* **ParedDetalle (0.8, 0.2, 0.0):** Un tono cálido con alta saturación que sirve como punto de énfasis visual.

> **Transformación de Escala:** A través de la propiedad `.scale.z`, se aplicó un factor de crecimiento de $1.5$ a los cubos de detalle, rompiendo la monotonía de la pared y demostrando la aplicación de matrices de escalamiento.


<img width="1823" height="919" alt="image" src="https://github.com/user-attachments/assets/9df41b99-1a6e-4037-aca8-fb0cd0e61e12" />


### 2.2 Algoritmo de Curvatura y Traslación
El pasillo original era una recta definida por un incremento constante en $Y$. Para la versión curva:
* Se introdujo una función de desplazamiento en $X$ que aumenta conforme avanza el índice $i$.
* Esto genera un giro a la izquierda, obligando a recalcular la posición de las paredes izquierda y derecha simultáneamente para mantener el ancho del pasillo constante.

<img width="1534" height="646" alt="image" src="https://github.com/user-attachments/assets/1c1170a1-f36f-4a3a-9cf7-2037e446c0af" />


### 2.3 Iluminación Dinámica
Se añadió una luz de tipo **Punto** con una energía de 1000 Watts. Su ubicación estratégica al final del pasillo permite generar un degradado de luz que se pierde hacia la entrada, acentuando la perspectiva y la curvatura del escenario.

### 2.4 Animación y Recorrido de Cámara
La cámara se configuró para actuar como un observador dentro del mundo. 
* **Ángulo Contrapicado:** Al situar la cámara cerca del suelo, se exagera la altura de las paredes, una técnica común en cinematografía para dar importancia al entorno.
* **Keyframing Procedural:** Se establecieron puntos clave de animación para que la cámara siga la curva del pasillo, manteniendo el foco en el centro de la escena.
<img width="595" height="242" alt="image" src="https://github.com/user-attachments/assets/bb2f85d8-6bec-4700-a53d-932622135e30" />




##  3. CONCLUSIÓN

El desarrollo de este escenario procedural permitió concluir los siguientes puntos clave sobre la graficación por computadora:

1. **Abstracción Matemática:** El éxito del giro a la izquierda dependió enteramente de la comprensión de los ejes de coordenadas. La graficación no es dibujo, es cálculo de posiciones.
2. **Eficiencia en el Diseño:** Mediante el script, es posible cambiar el "largo_pasillo" de 10 a 1000 en segundos, algo imposible en modelado manual.
3. **Integración Sensorial:** La combinación de materiales RGB, luces y una cámara animada transforma una geometría simple en una experiencia inmersiva, demostrando que la técnica (código) y la estética (diseño) son inseparables.

En conclusión, este proyecto cumple con los requerimientos de la Unidad I al demostrar el dominio de las herramientas de software (Blender/Python) y los fundamentos teóricos (matemáticas y color) que rigen la graficación moderna.
