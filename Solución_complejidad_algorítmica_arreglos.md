# Taller - Complejidad algorítmica y Arreglos (Respuestas)
**SD1004 · Estructura de Datos** - Institución Universitaria Pascual Bravo
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

## Parte 2 - Arreglos 1D

### 2.1 Diseñar arreglo

** 1. Arreglo `notas` de 6 casillas:**

| índice | 0 | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|---|
| Valor | 3.5 | 4.2 | 2.8 | 5.0 | 3.9 | 4.5 |

**2.** La tercera nota ingresada tiene como índice 2, con valor 2.8

**3.** Pseudo código
ultima_nota = notas[logitud(notas) - 1] 

### 2.2 Direcciones en memoria

Usando la formula: `direccion = base + (índice * tamaño)` teniendo como base `0x2000` y un tamaño de `4 bytes` las ubicaciones dan en:

- `notas[0]` = 0x2000 + (0 * 4) = **0x2000**
- `notas[3]` = 0x2000 + (3 * 4) = 0x2000 + 12 = **0x200C**
- `notas[5]` = 0x2000 + (5 * 4) = 0x2000 + 20 = **0x2014**

**2.** Acceder a `notas[3]` tiene la misma velocidad que acceder a `notas[0]` porque ambos escenarios el computador calcula la dirección con una multiplicación y una suma; no tiene que recorrer el arreglo completo de inicio a fin. ya que el calculo toma el mismo número de operaciones sin importar el índice.

### 2.3 Búsqueda lineal vs binaria

Arreglo: `edades = [15, 18, 20, 23, 27, 31, 35, 40]` - Buscar valor `31`

**1. Búsqueda lineal**

| Paso | Indice revisado | valor | ¿Es 31? |
|---|---|---|---|
| 1 | 0 | 15 | No |
| 2 | 1 | 18 | No |
| 3 | 2 | 20 | No |
| 4 | 3 | 23 | No |
| 5 | 4 | 27 | No |
| 6 | 5 | 31 | Sí |

Se realizaron 6 comparaciones para dar el con el valor que se buscaba.

**2. Búsqueda binaria**

| Paso | low | high | mid | edades[mid] | resultado |
|---|---|---|---|---|---|
| 1 | 0 | 7 | 3 | 23 | 23 < 31 -> buscar a la derecha, low = 4 |
| 2 | 4 | 7 | 5 | 31 | Valor encontrado | 

Se realizaron 2 comparaciones para dar el con el valor que se buscaba.

**3.** La búsqueda binaria solo funciona si el arreglo está ordenado porque en cada paso decide hacía donde ir buscando, es decir, izquierda o derecha, y en cada paso compara el valor que se esta buscando con el elemento  del medio. Esto solo es válido si sabemos que todo lo que está antes es menor y todo lo que esta después es mayor, y viceversa.

**4.** Con un millón de elementos creo que seguiría usando la **búsqueda binaria** porque  con un millón de elementos solo necesitaría aproximadamente 20 comparaciones a diferencia de la líneal donde tendría que revisar en el peor de los casos la totalidad de elementos llegando a revisar el millón de elementos.

### 2.4 Insertar un elemento

`edades = [15, 18, 20, 23, 27]` un arreglo de 5 casillas

**1.** En el escenario donde tenemos un espacio disponible, es muy barato insertar un nuevo valor ya que simplemente colocamos el valor en la siguiente casilla libre. Sin embargo, en el escenario donde no tenemos espacio disponible tendríamos que crear un arreglo más grande y copiar todos los elementos existentes al nuevo arreglo antes de agregar el nuevo valor.

**2.** Insertar el valor `21` en la mitad requiere desplazar una posición a la derecha todos los elementos que quedan posterior del punto de inserción.

**3.** Comparación Big O

| Caso | Complejidad |
|---|---|
|Insertar al final, con espacio| O(1) |
|Insertar al final, sin espacio (crear nuevo arreglo) | O(n) |
|Insertar en la mitad (desplazando elementos) | O(n) |

---

## Parte 3 — Arreglos 2D
 
### 3.1 Diseña la matriz
 
**1. Matriz `salon` (3 filas × 4 columnas):**
 
|            | col 0 | col 1 | col 2 | col 3 |
|---|---|---|---|---|
| **fila 0** | [0][0] | [0][1] | [0][2] | [0][3] |
| **fila 1** | [1][0] | [1][1] | [1][2] | [1][3] |
| **fila 2** | [2][0] | [2][1] | [2][2] | [2][3] |
 
**2.** Pseudocódigo para acceder a fila 2, columna 3:
 
```
salon[2][3]
```
 
**3.** Total de casillas: **3 × 4 = 12**. En general, el total de casillas de una matriz se calcula como `filas × columnas`.
 
### 3.2 De 2D a memoria (row-major)
 
**1.** Aplanado en memoria (fila por fila, row-major), las 12 casillas quedan en este orden:
 
```
[0][0] [0][1] [0][2] [0][3] [1][0] [1][1] [1][2] [1][3] [2][0] [2][1] [2][2] [2][3]
  pos0   pos1   pos2   pos3   pos4   pos5   pos6   pos7   pos8   pos9  pos10  pos11
```
 
**2.** Fórmula: `dirección = base + ((fila × número_de_columnas + columna) × tamaño)`, con base = 0x1000, columnas = 4, tamaño = 4 bytes.
 
- `[1][2]`: posición aplanada = (1 × 4 + 2) = 6 → 6 × 4 = 24 bytes → 0x1000 + 24 = **0x1018**
**3.**
- `[0][0]`: posición = (0 × 4 + 0) = 0 → 0x1000 + 0 = **0x1000**
- `[2][3]`: posición = (2 × 4 + 3) = 11 → 11 × 4 = 44 bytes → 0x1000 + 44 = **0x102C**

### 3.3 Recorrido con ciclos anidados
 
**1.** Pseudocódigo:
 
```
contador = 0
para fila desde 0 hasta f-1:
    para columna desde 0 hasta c-1:
        si salon[fila][columna] == 1:
            contador = contador + 1
```
 
**2.** La complejidad es **O(f × c)**. Por cada una de las `f` filas se recorren las `c` columnas, así que el ciclo interno se ejecuta `c` veces por cada una de las `f` iteraciones del ciclo externo, dando un total de `f × c` casillas visitadas.
 
**3.** Si `f` y `c` se duplican ambos a la vez, el trabajo total se multiplica por **4** (2 × 2), ya que el tiempo depende del producto f × c, no de f o c por separado.

### 3.4 Conectando todo

Según en lo que he podido entender, Big O es una herramienta que nos permite predecir cómo va a crecer el tiempo de un algoritmo antes de pensar en ejecutarlo con n cantidad de datos, esto es algo que necesitamos para decidir cómo estructurar y recorrer daatos. Un arreglo 1D nos da acceso O(1) a cualquier posición por índice gracias al calculo aritmético de memoria base, por otro lado, un arreglo 2D, al necesitar dos índices, los cuales serían fila y columna, sigue siendo O(1) para acceder a una casilla puntual, pero recorrerlo completo cuesta O(f x c) porque hay que revisar  cada combinación de fila y columna. Comprender Big O nos ayuda a anticipar como escalará una solución y saber que estrategia de búsqueda utilizar.
