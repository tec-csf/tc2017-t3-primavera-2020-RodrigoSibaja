# Tarea *3*. *Técnicas de diseño de algoritmos*

---

##### Integrantes:
1. *Rodrigo Sibaja Villarreal* - *A01023121* - *CSF*

---
## 1. Aspectos generales

Las orientaciones de la tarea se encuentran disponibles en la plataforma **Canvas**.

Este documento es una guía sobre qué información debe entregar como parte de la tarea, qué requerimientos técnicos debe cumplir y la estructura que debe seguir para organizar su entrega.


### 1.1 Requerimientos técnicos

A continuación se mencionan los requerimientos técnicos mínimos de la tarea, favor de tenerlos presente para que cumpla con todos.

* El código debe desarrollarse en C++, cumpliendo con el último estándar [C++17](https://isocpp.org/std/the-standard).
* Toda la programación debe realizarse utilizando Programación Genérica.
* Deben utilizarse las [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).
* Todo el código debe estar correctamente documentado, siguiendo los lineamientos que aparecen en [Documenting C++ Code](https://developer.lsst.io/cpp/api-docs.html).
* Todo el código de la tarea debe alojarse en este repositorio de GitHub.
* Debe configurar su repositorio para que utilice el sistema de Integración Continua [Travis CI](https://travis-ci.org/).

### 1.2 Estructura del repositorio

El proyecto debe seguir la siguiente estructura de carpetas:
```
- / 			        # Raíz del repositorio
    - README.md			# Archivo con la información general de la actividad (este archivo)
    - sources  			# Códigos fuente con la solución
    - examples			# Archivos de ejemplo que pueden utilizarse para verificar que la solución funciona.
```

## 2. Solución

El primer problema a resolver fue una implementación del algoritmo de Strassen para multiplicar dos matrices, este método permite realizar la multiplicación de matrices utilizando 7 multiplicaciones escalares, una mejora al método clásico que utiliza 8 multiplicaciones. Este algoritmo se encarga de dividir dos matrices cuadradas de orden 2 en cuatro matrices de n/2 x n/2, al dividir el problema en cuatro subproblemas a resolver similares, estamos empleando la técnica de diseño "Divide y venceras". Este método requiere del uso de más sumas que la versión clásica, pero su relevancia se debe a la reducción de una multiplicación que se refleja en el orden de complejidad del método como O(n^2.81), a comparación del método clásico cuyo orden de complejidad es O(n^3).
Dadas dos matrices cuadradas de orden 2, A y B, tal algoritmo se basa en obtener la matriz producto C mediante las siguientes fórmulas:

c11 = m1 + m2 – m4 + m6
c12 = m4 + m5
c21 = m6 + m7
c22 = m2 – m3 + m5 – m7
donde los valores de m1, m2, ..., m7 vienen dados por:
m1 = (a12 – a22)(b21 + b22)
m2 = (a11 + a22)(b11 + b22)
m3 = (a11 – a21)(b11 + b12)
m4 = (a11 + a12)b22
m5 = a11(b12 – b22)
m6 = a22(b21 – b11)
m7 = (a21 + a22)b11


El segundo problema a resolver fue la implementación de un algoritmo que coloree un grafo dado, utilizando números para representar colores, de tal manera que dos o más vertices adyacentes no tengan asignado el mismo color. El programa crea el grafo a utilizar junto con sus vertices y conexiones de aristas. El programa despues utiliza un metodo para asignar colores en el que toma un vertice y revisa el color de los vertices adyacentes, de esta forma reconoce cuales no utilizar, y le asigna el primer color disponible de la lista de colores, se avanza al siguiente vertice y se repite el proceso hasta que todos los vertices hayan sido coloreados. El orden de complejidad de este programa es de O(n^2).
El resultado obtenido utilizando esta solución es correcto mas no necesariamente el más optimo para colorear utilizando el menor número de colores, los resultados son dependientes de la aproximación que se tenga al problema, generando así varias soluciones prometedoras que cumplen una restricción, por lo que se concluye que este programa utiliza la técnica de diseño de algoritmos ávidos.

### 2.1 Pasos a seguir para utilizar la aplicación

1. Iniciar terminal del equipo.

2. Acceder al directorio donde se quiere clonar el repositorio.

3. Utilizar el comando "git clone" seguido por el link del repositorio: https://github.com/tec-csf/tc2017-t3-primavera-2020-RodrigoSibaja.git

4. Acceder a la carpeta sources y correr alguno de los códigos

Strassen

5. Compilar utilizando el comando "g++ algStrassen.cpp -o strassen" y correr el programa con el comando "./strassen".

6. Seguir las instrucciones del programa (multiples valores pueden ser instertados si estan separados por un espacio).

Coloreo de grafos

5. Compilar utilizando el comando "g++ coloreoGrafos.cpp -o grafos" y correr el programa con el comando "./grafos".

6. El programa ya tiene dos grafos definidos con los que trabaja, es necesario cambiar el código para obtener diferentes resultados.

## 3. Referencias

Guerequeta, R., Vallecido, A. (1998). Técnicas de Diseño de Algoritmos. [online] Recuperado de: http://www.lcc.uma.es/~av/Libro/
GeeksforGeeks. (2014). Graph Coloring | Set 2 (Greedy Algorithm). [online] Recuperado de: https://www.geeksforgeeks.org/graph-coloring-set-2-greedy-algorithm/
Srikanth, K. (2020). Strassen’s Matrix Multiplication algorithm. [online] Recuperado de: https://iq.opengenus.org/strassens-matrix-multiplication-algorithm/ 
