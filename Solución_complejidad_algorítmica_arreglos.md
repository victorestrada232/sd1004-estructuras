# Taller - Complejidad algorítmica y Arreglos (Respuestas)
**SD1004 · Estructura de Datos ** - Institución Universitaria Pascual Bravo
Docente: Juan Duque · Semestre 2026-II
Estudiante: Víctor Manuel Estrada

---

## Parte 1 - Complejidad Algorítmica (Big O)

### 1.1 Clasifica la complejidad

1. La respuesta es O(log n), ya que cada vez que se abre por la mitad se descarta la otra mitad de páginas. El espacio de búsqueda se reduce a la mitad en cada paso, por lo que el número de pasos crece muy lentamente aunque el diccionario sea enorme.

2. La respuesta es O(n), en el peor de los casos que el elemento que necesitemos este al final, se debe inspeccionar los n elementos uno a uno. El tiempo crecerá en proporción directa a la cantidad de elementos que existan.

3. La respuesta es O(1), sin importar cuántas cartas tenga el mazo, siempre tomará el mismo tiempo.

4. La respuesta para esta es O(n²), por cada estudiante se deberá compararlo con los demás, así que el algoritmo hace aproximadamente n x n comparaciones, un ciclo anidado dentro de otro.

5. La respuestqa es O(1) Es una lecturea directa y no depende cuántos elementos haya.


### 1.2 De la vida real  al análisis

**Tarea O(n):**  Si un salón tiene el doble de estudiantes, pues se necesitaría realizar el doble de entregas y por consiguiente el doble de tiempo, ya que hay una relación directa entre la cantidad de estudiantes y el tiempo que tomaría la tarea.

**Si n se hace 10 veces más grande:** El tiempo que tomaría la tarea se haría también 10 veces más grande, porque cada elemento adicional agrega la misma cantidad de trabajo.

### 1.3 ¿Cuál escala mejor?

 Yo en lo personal recomendaría la forma O(n log n), aunque A sea más eficiente; en el caso que n se vuelva más grande, O(n log n) mantendrá el rendimiento sostenible, mientras que la forma  O(n²) podría colapsar el sistema.

 ### 1.4 Verdadero o falso

 **a. Falso** > Es falso porque Big O no mide segundos reales, sino cómo crece el tiempo con el tamaño de los datos; Es decir, Big O compara las tendencias de crecimiento, no las velocidades absolutas.

 **b. Verdadero** > Es verdadero porque Big O describe la tasa de crecimiento del tiempo de ejecución a medida que crece el tamaño de la entrada. no un número x de segundos concreto que depende del hardware y otros.

 **c. Falso** > Es falso porque acceder a `arreglo[5]` es O(1). y es así porque los arreglos permiten acceso directo a las posiciones. y su posición en memoria se calcula con base + índice * tamaño, por lo que no hay necesidad de recorrer los elementos anteriores.
