# Métodos Numéricos 

## Proyecto #2: Documento Explicativo + Capturas de pantalla

### Integrantes:
* Campos Granados María José :grin:
* Ramírez Ochoa Fernanda Monserrat :octocat:
* Rocha Avila Emmanuel :neckbeard:

**Carrera:** Ingeniería en Sistemas Computacionales

**Profesor:** Dr. Zamudio Rodríguez Víctor Manuel

**Fecha de entrega de CD:** 11 de Abril de 2018

## A. Método Bisección.

*(También conocido como: "de corte binario", "de partición de 
intervalos" o "de Bolzano")*

El signo de f(x) cambia a ambos lados de la raíz. Si f(x) es real y continúa en el intervalo que va desde Xl hasta Xu y f(Xl) y f(Xu) tienen signos opuestos, es decir,

![Bis - Pic 1](DEPI23.jpg)

entonces hay al menos una raíz real entre xl y xu.

Los métodos de búsqueda incremental aprovechan esta  característica localizando un intervalo en el que la función cambie de signo. Entonces, la localización del cambio de signo (y, en consecuencia, de la raíz) se logra con más exactitud al dividir el intervalo en varios subintervalos.

Se investiga cada uno de estos subintervalos para encontrar el cambio de signo. El proceso se repite y la aproximación a la raíz mejora cada vez más en la medida que los subintervalos se dividen en intervalos cada vez más pequeños.

Es un tipo de búsqueda incremental en el que el intervalo se 
divide siempre a la mitad. Si la función cambia de signo sobre un intervalo, se evalúa el valor de la función en el punto medio. La posición de la raíz se determina situándola en el punto medio del subintervalo, dentro del cual ocurre un cambio de signo. El proceso se repite hasta obtener una mejor aproximación.

**Algoritmo de bisección**
![Bis - Pic 2](DEPI24.jpg)

## B. Método de la Secante.
<div style="text-align: justify"> 
    Un problema potencial en la implementación del método de Newton-Raphson es la evaluación de la derivada. Existen algunas funciones cuyas derivadas en ocasiones resultan muy difíciles de calcular. En dichos casos, la derivada se puede aproximar mediante una diferencia finita dividida hacia atrás, como en: 
</div>

![Sec - Img 1](DEPI01.jpg)

y al sustituirlo en la ecuación:

![Sec - Img 2](DEPI02.jpg)

se obtiene la expresión:

![Sec - Img 3](DEPI03.jpg)

Algoritmo:

1. Tome “ i = 2 ” 
2. Mientras “ i ≤ No ” haga 3 – 6
3. ![Sec - Paso 3](DEPI05.jpg)
4. Si “ fp = 0 ” ó fp < TOL entonces salida P (Exit) stop.
5. i = i + 1
6. ![Alg - Sec - Paso 6](DEPI06.jpg)
7. Salida: el método fracasó después de “ No ” iteraciones.

Ejemplo de aplicación del método:

![Ejemplo - Secante](DEPI09.jpg)

## C. Método de Newton-Raphson.

<div style="text-align: justify">
    En cálculo diferencial, se conoce como el método de Newton-Raphson a la función iterativa desarrollada por Isaac Newton para aproximar los ceros de una función cualquiera, valiéndose solamente de la función misma y su derivada.
</div>
<br>
<div style="text-align: justify">
    El proceso iterativo es bastante útil para encontrar, por ejemplo, las raíces de una función cúbica con ceros no necesariamente enteros o racionales (irracionales, no complejos) los cuales serían difíciles de encontrar con los métodos tradicionales como la factorización.
</div>
<br>
<div style="text-align: justify">
    Dado un valor inicial x, que idealmente podría ser un valor cercano a la raíz, evaluamos la función en dicho valor, luego encontramos la ecuación de la recta tangente a la función en ese punto, encontramos luego su respectivo intercepto con el eje x. 
</div>

![New - Pic 1](DEPI19.jpg)

<div style="text-align: justify">
    Ese numero se toma como valor siguiente y se vuelve a hacer el proceso. Eventualmente llegaremos a la raíz con una buena aproximación decimal, mientras más iteraciones se hacen, más preciso es el resultado.
</div>

#### Geométricamente se ve así:

![New - Pic 2](DEPI20.gif)

##### Ejemplo de aplicación del método:

**Planteamiento del problema:** Utilice el método de Newtón- Raphson para calcular la raíz de f(x)= e^-x -1 empleando como valor inicial  Xo = 0 . 

**Solución:** La primera derivada de la función es f´(x)= -e^-x -1 que se sustituye junto con la función original en la ecuación para tener:

![New - Pic 3](DEPI21.jpg)

Empezando con un valor inicial Xo=0, se aplica está ecuación iterativa para calcular.

<div style="text-align: justify">
 Así el método converge rápidamente a
 la raíz verdadera. Observe el que error
 relativo porcentual verdadero en cada
 iteración disminuye mucho más rápido
 con la iteración simple de punto fijo 
</div>

![New - Pic 4](DEPI22.jpg)

1. Escoger un valor inicial (Xi).
2. La primera aproximación de la raíz es el valor (Xr) para el que la recta tangente a la función f(x) en el punto (Xi, f(Xi)) cruza el eje de las “x”.
4. Calcular una nueva aproximación a la raíz
5. Verificar si la nueva aproximación es tan exacta como se desea.

*Si es así los cálculos terminan / De otro modo regrese al paso 3.*

## D. Método de la Regla falsa.

*(También llamado “Método de Falsa Posición”, “Método Regula-Falsi” y “Método de Interpolación Lineal”)*

<div style ="text-align: justify">
    Pertenece a los métodos que utilizan intervalos, es un método que aprovecha una visualización gráfica que consiste en unir f(a) y f(b) con una línea recta. La intersección de esta línea con el eje de las x representa una mejor aproximación de la raíz (siguiente b ó a). El hecho de que se reemplace la curva por una línea recta da una “falsa posición” de la raíz; de aquí el nombre de método de la falsa posición, o en latín, “regula falsi”.
</div>

![False - Pic 1](DEPI11.jpg)

Usando triángulos semejantes, la intersección de la línea recta con el eje de las x se estima mediante:

![False - Pic 2](DEPI07.jpg)

en la que se despeja “x”:

![False - Pic 3](DEPI08.jpg)

En esta expresión aparece la relación:

![False - Pic 4](DEPI10.jpg)

que es equivalente al inverso de la derivada de primer orden de la función:

![False - Pic 5](DEPI12.jpg)

La ecuación resultante es: 

![False - Pic 6](DEPI13.jpg)

<div style ="text-align: justify">
    La velocidad de convergencia de este método es muy superior a la del método de la bisección cuando ambos puntos están lejos de la solución. Sin embargo su eficiencia ya no es tan evidente cuando un punto esta distante de la solución y el otro esta muy cercano a ella. 
</div>

Algoritmo:

1. Toma “ i = 0 ”
2. Mientras “ i ≤ No ” haga 3 a 6.
3. Se asignan:
 * fa = f(a)
 * fb = f(b)
 * ![False - Pic 7](DEPI14.jpg)
 * fp = f(p)
4. Si ![False - Pic 8](DEPI16.jpg) entonces salida P (Raiz) (Exit) stop
5. i = i + 1
6. Si ![False - Pic 9](DEPI17.jpg)
7. El método fracaso después de “ No ” iteraciones

Ejemplo de aplicación:

![False - Pic 10](DEPI18.jpg)

## E. Anexo - Capturas de pantalla

*Menú principal de la aplicación*
![Capturas - Cap 02](CAP05.png)

*Métodos de la unidad 2 (Proyecto Actual)*
![Capturas - Cap 05](CAP01.png)

*Unidad 1 (Proyecto Anterior)*
![Capturas - Cap 04](CAP04.png)

*Introducimos los parámetros*
![Capturas - Cap 06](CAP06.png)

*Al oprimir "BISECCIÓN" se muestra el resultado.*
![Capturas - Cap 08](CAP08.png)

*En la consola se ve la tabla resultante (Explicación vocal pendiente)*
![Capturas - Cap 10](CAP10.png)

*En la consola se ve la tabla resultante (Explicación vocal pendiente)*
![Capturas - Cap 11](CAP11.png)

*Al oprimir "SECANTE" se muestra el resultado.*
![Capturas - Cap 18](CAP18.png)

*En la consola se ve la tabla resultante (Explicación vocal pendiente)*
![Capturas - Cap 15](CAP15.png)
![Capturas - Cap 16](CAP16.png)
