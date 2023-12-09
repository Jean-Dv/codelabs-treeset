author: Jean-Dv
summary:
id: treeset
tags: code java data-structures
categories: code
environments: Web
status: Published
feedback link: https://github.com/Jean-Dv/codelabs-treeset/blob/master/markdown/treeset

# Treeset Data Structure

## Método `add(O object)`

Duration: 0:01:00

### Paso a paso

El método `add` se utiliza para agregar un elemento al conjunto o colección.
Aquí explicaremos cómo funciona visualmente paso a paso:

#### Paso 1: Inserción del primer elemento

Supongamos que tenemos un TreeSet vacío y queremos agregar el elemento "C".
En este caso, el árbol se vería así:

![Tree with C](img/treeset-add-1.png)

#### Paso 2: Inserción del segundo elemento

Ahora, si queremos agregar el elemento "A", se compara con el elemento
existente ("C") y se decide que "A" es menor, por lo que se coloca
a la izquierda:

![Tree C and A](img/treeset-add-2.png)

#### Paso 3: Inserción del tercer elemento

Añadimos el elemento "B", que es mayor que "A" pero menor que "C", por lo que
se coloca a la derecha de "A" y a la izquierda de "C":

![Tree C, A, B](img/treeset-add-3.png)

### Complejidad temporal:

La complejidad temporal de `add` en un TreeSet es O(log N), donde N es el número
de elementos en el conjunto. Debido a la estructura del árbol de busqueda binaria,
las inserciones se realizan eficientemente.

### Ejemplo de código:

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<String> treeSet = new TreeSet<>();

        // Agregar elementos usando el método add
        treeSet.add("C");
        treeSet.add("A");
        treeSet.add("B");

        // Mostrar el TreeSet
        System.out.println("TreeSet: " + treeSet);
    }
}
```

### Conclusión:

El método `add` mantiene la propiedad de orden en el TreeSet, asegurando que
los elementos se ubiquen correctamente en el árbol.

## Método `addAll(Collection<? extends E> c)`

Duration: 0:01:00

### Paso a paso

#### Paso 1: Creación de TreeSet y Collection

```java
import java.util.TreeSet;
import java.util.ArrayList;
import java.util.Collection;

public class TreeSetExample {
    public static void main(String[] args) {
        TreeSet<String> treeSet = new TreeSet<>();
        treeSet.add("A");
        treeSet.add("B");
        treeSet.add("C");
        Collection<String> collection = new ArrayList<>();
    }
}
```

#### Paso 2: Agregar elementos a la colección

```java
collection.add("D");
collection.add("E");
collection.add("F");
```

#### Paso 3: Uso del método `addAll`

```java
treeSet.addAll(collection);
```

### Funcionamiento en un árbol de busqueda binaria

Antes de ejecutar el método `addAll`, el árbol se ve así:

![Tree C, A, B](img/treeset-add-3.png)

Después de ejecutar el método `addAll`, el árbol se ve así:

![Tree C, A, B](img/treeset-addAll-1.png)

### Complejidad temporal:

La complejidad temporal de addAll en un TreeSet depende de la cantidad de
elementos en la colección a agregar. Si la colección tiene N elementos,
la complejidad sería O(N \* log N).

### Conclusión:

El método addAll permite agregar todos los elementos de una colección al TreeSet,
manteniendo la propiedad de orden en el árbol de búsqueda binaria.

## Método `ceiling(E e)`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
        treeSet.add(3);
        treeSet.add(6);
    }
}
```

#### Paso 2: Uso del método `ceiling(E e)`

```java
 // Obtener el elemento igual o mayor al elemento especificado
Integer ceilingElement = treeSet.ceiling(4);

// Imprimir el elemento obtenido (o null si no hay elemento mayor o igual)
System.out.println("Elemento igual o mayor a 4: " + ceilingElement);
```

### Funcionamiento del método:

El método `ceiling(e)` devuelve el elemento igual o mayor al elemento especificado (e). En este caso, dado que hemos agregado los números 5, 2, 8, 3 y 6, el elemento igual o mayor a 4 es 5.

Resultado esperado:

```java
Elemento igual o mayor a 4: 5
```

### Conclusión:

El método `ceiling(e)` es útil para encontrar el primer elemento igual o mayor al valor especificado en el conjunto.

### Nota adicional:

- Si no hay un elemento igual o mayor al especificado, el método devuelve null.
- Este método puede ser especialmente útil cuando se necesita encontrar el siguiente elemento más grande o igual en un conjunto ordenado.

## Método `clear()`

## Método `clone()`

## Método `comparator()`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación de TreeSet con comparador personalizado

```java
import java.util.TreeSet;
import java.util.Comparator;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet con comparador personalizado (orden inverso)
        TreeSet<String> treeSet = new TreeSet<>(Comparator.reverseOrder());

        // Agregar elementos al TreeSet
        treeSet.add("C");
        treeSet.add("A");
        treeSet.add("B");
    }
}
```

#### Paso 2: Uso del método `comparator`

```java
Comparator<String> comparator = treeSet.comparator();
System.out.println("Comparador: " + comparator);
```

### Funcionamiento del método:

En este ejemplo, el comparador utilizado es `Comparator.reverseOrder()`, lo que significa
que los elementos se ordenarán en orden inverso al orden natural.

Resultado esperado:

```java
Comparador: java.util.Collections$ReverseComparator@hashcode
```

### Conclusión:

- Si se utiliza un comparador personalizado, el método `comparator` devolverá ese comparador
- Si no se proporciona un comparador al crear el `TreeSet`, el método `comparator` devolvera `null`, indicando que se está utilizando el orden natural de los elementos.

### Nota adicional:

Si el conjunto se creó utilizando el orden natural de los elementos, `comparator` devolverá
`null`.

## Método `contains(Object o)`

## Método `descendingIterator?()`

## Método `descendingSet()`

## Método `first()`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreesetExample {
    public static void main(String[] args) {
        // Crea a un TreeSet
        TreeSet<Integer> tree = new TreeSet<Integer>();

        // Agrega elementos
        tree.add(14);
        tree.add(8);
        tree.add(200);
        tree.add(48);
        tree.add(7);
        tree.add(124);
    }
}

```

#### Paso 2: Uso del método `first`

```java
 // Mostrando el elemento más bajo del Treeset
    System.out.println("El primer elemento es: " + tree.first());
```

### Funcionamiento del método:

El método devuelve el elemento más bajo en el Treeset. Si los elementos son de tipo cadena, se verifican en orden alfabético y si los elementos son de tipo entero, se devuelve el número entero más pequeño, en este caso el 7

Resultado esperado:

```java
El primer elemento es: 7
```

### Conclusión:

- El método first() es útil para obtener el primer elemento del conjunto.
- A diferencia de `pollFirst()`, `first()` no elimina el elemento del conjunto.

### Nota adicional:

El método `first()` en un TreeSet proporciona una manera eficiente de acceder al primer elemento del conjunto sin realizar ninguna modificación en la estructura del conjunto, permitiendo operaciones de solo lectura de manera eficiente.

## Método `floor?(E e)`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(10);
        treeSet.add(5);
        treeSet.add(15);
        treeSet.add(7);
        treeSet.add(12);
    }
}
```

#### Paso 2: Uso del método `floor?(E e)`

```java
// Obtener el elemento igual o menor al elemento especificado
Integer floorElement = treeSet.floor(9);

// Imprimir el elemento obtenido (o null si no hay elemento menor o igual)
System.out.println("Elemento igual o menor a 9: " + floorElement);
```

### Funcionamiento del método:

El método `floor?(E e)` devuelve el elemento igual o menor al elemento especificado (e). En este caso, dado que hemos agregado los números 10, 5, 15, 7 y 12, el elemento igual o menor a 9 es 7.

Resultado esperado:

```java
Elemento igual o menor a 9: 7
```

### Conclusión:

El método `floor?(e)` es útil para encontrar el primer elemento igual o menor al valor especificado en el conjunto.

### Nota adicional:

Desde la perspectiva de la estructura del árbol subyacente en un TreeSet, el método `floor?(e)` busca el nodo más bajo en el árbol que sea igual o menor al valor especificado (e).

## Método `subSet(fromElement, toElement)`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
        treeSet.add(3);
        treeSet.add(6);
    }
}
```

#### Paso 2: Uso del método `subSet(fromElement, toElement)`

```java
// Obtener un subconjunto desde el elemento de inicio hasta el elemento final (exclusivo)
TreeSet<Integer> subSet = new TreeSet<>(treeSet.subSet(3, 6));

// Imprimir el subconjunto
System.out.println("Subconjunto desde el elemento 3 hasta el elemento 6 (exclusivo): " + subSet);
```

### Funcionamiento del método:

El método `subSet(fromElement, toElement)` devuelve un subconjunto del conjunto original que contiene todos los elementos mayores o iguales al elemento de inicio (fromElement) y estrictamente menores que el elemento final (toElement). En este caso, dado que hemos agregado los números 5, 2, 8, 3 y 6, el subconjunto contendrá los elementos 3 y 5.

Resultado esperado:

```java
Subconjunto desde el elemento 3 hasta el elemento 6 (exclusivo): [3, 5]
```

Demostración en un árbol de busqueda binaria

![Tree 5, 2, 8, 3, 6](img/subset.png)

### Conclusión:

El método `subSet(fromElement, toElement)` es útil para obtener un subconjunto que abarca desde el elemento de inicio (inclusive) hasta el elemento final (exclusivo).

### Nota adicional:

Al emplear `subSet(fromElement, toElement)`, es crucial recordar que el elemento final (toElement) no se incluirá en el subconjunto resultante. Este método es efectivo cuando necesitas una porción específica del conjunto original, delimitada por dos valores

## Método `tailSet(fromElement)`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
        treeSet.add(3);
        treeSet.add(6);
    }
}
```

#### Paso 2: Uso del método `tailSet(fromElement)`

```java
// Obtener un subconjunto desde el elemento especificado (inclusivo)
TreeSet<Integer> tailSet = new TreeSet<>(treeSet.tailSet(3));

// Imprimir el subconjunto
System.out.println("Subconjunto desde el elemento 3 (inclusivo): " + tailSet);
```

### Funcionamiento del método:

El método `tailSet(fromElement)` devuelve un subconjunto del conjunto original que contiene todos los elementos mayores o iguales al elemento especificado (fromElement). En este caso, dado que hemos agregado los números 5, 2, 8, 3 y 6, el subconjunto contendrá los elementos 3, 5, 6 y 8.

Resultado esperado:

```java
Subconjunto desde el elemento 3 (inclusivo): [3, 5, 6, 8]
```

Demostración en un árbol de busqueda binaria

![Tree 5, 2, 8, 3, 6](img/Tailset.png)

### Conclusión:

El método `tailSet(fromElement)` es útil para obtener un subconjunto que contiene todos los elementos mayores o iguales al elemento especificado.

### Nota adicional:

- Al utilizar `tailSet(fromElement)`, es esencial recordar que el subconjunto devuelto incluirá el elemento especificado (fromElement). Este método es útil cuando necesitas todos los elementos mayores o iguales a un valor particular en el conjunto original.

- Similar a `headSet(toElement)`, el subconjunto devuelto es una vista respaldada por el conjunto original. Cualquier cambio en el conjunto original se reflejará en el subconjunto y viceversa. Esta característica permite trabajar eficientemente con porciones específicas del conjunto sin duplicar datos.

## Método `headSet(Object toElement)`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
        treeSet.add(3);
        treeSet.add(6);
    }
}
```

#### Paso 2: Uso del método `headSet(toElement)`

```java
// Obtener un subconjunto hasta el elemento especificado
TreeSet<Integer> headSet = new TreeSet<>(treeSet.headSet(6));

// Imprimir el subconjunto
System.out.println("Subconjunto hasta el elemento 6: " + headSet);
```

### Funcionamiento del método:

El método `headSet(toElement)` devuelve un subconjunto del conjunto original que contiene todos los elementos estrictamente menores que el elemento especificado (toElement). En este caso, dado que hemos agregado los números 5, 2, 8, 3 y 6, el subconjunto contendrá los elementos 2, 3 Y 5.

Resultado esperado:

```java
Subconjunto hasta el elemento 6 (exclusivo): [2, 3, 5]
```

Demostración en un árbol de busqueda binaria

![Tree 5, 2, 8, 3, 6](img/Headset.png)

### Conclusión:

El método headSet(toElement) es útil para obtener un subconjunto que contiene todos los elementos estrictamente menores que el elemento especificado.

### Nota adicional:

El subconjunto devuelto es una vista respaldada por el conjunto original, por lo que cualquier cambio en el conjunto original se reflejará en el subconjunto y viceversa.

## Método `higher(E e)`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(10);
        treeSet.add(5);
        treeSet.add(15);
        treeSet.add(7);
        treeSet.add(12);
    }
}
```

#### Paso 2: Uso del método `higher(E e)`

```java
// Obtener el primer elemento estrictamente mayor al elemento especificado
Integer higherElement = treeSet.higher(9);

// Imprimir el elemento obtenido
System.out.println("Primer elemento estrictamente mayor a 9: " + higherElement);
```

### Funcionamiento del método:

El método `higher(E e)` devuelve el primer elemento estrictamente mayor al elemento especificado (e). En este caso, dado que hemos agregado los números 10, 5, 15, 7 y 12, el primer elemento estrictamente mayor a 9 es 10.

Resultado esperado:

```java
Primer elemento estrictamente mayor a 9: 10
```

### Conclusión:

El método `higher(e)` es útil para encontrar el primer elemento estrictamente mayor al valor especificado en el conjunto.

### Nota adicional:

- Si no hay un elemento estrictamente mayor al especificado, el método devuelve null.
- Este método es eficiente en conjuntos ordenados, ya que aprovecha la estructura jerárquica del árbol para realizar búsquedas de manera eficaz.

## Método `isEmpty()`

## Método `iterator()`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación de TreeSet y agregar elementos

```java
import java.util.TreeSet;
import java.util.Iterator;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<String> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add("C");
        treeSet.add("A");
        treeSet.add("B");
    }
}
```

#### Paso 2: Uso del método `iterator`

```java
Iterator<String> iterator = treeSet.iterator();

// Iterar sobre los elementos e imprimirlos
while (iterator.hasNext()) {
    System.out.println(iterator.next());
}

```

### Funcionamiento del método:

El método `iterator` devuelve un iterador que proporciona acceso a los elementos en el `TreeSet`.
En este caso, al imprimir los elementos, se mostrarán en orden ascendente debido a la naturaleza
del árbol de búsqueda binaria.

Resultado esperado:

```
A
B
C
```

### Conclusión:

- El método `iterator` proporciona un iterador que permite recorrer los elementos del `TreeSet` en orden ascendente.

### Nota adicional:

- Puedes utilizar un bucle `for` mejorado (`foreach`) para simplificar el código al iterar sobre el `TreeSet`.

```java
for (String element : treeSet) {
    System.out.println(element);
}
```

## Método `last()`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación del Treeset y agrega elementos

```java
import java.util.TreeSet;

public class TreesetExample {
    public static void main(String[] args) {
        // Crea a un TreeSet
        TreeSet<Integer> tree = new TreeSet<Integer>();

        // Agrega elementos
        tree.add(14);
        tree.add(8);
        tree.add(200);
        tree.add(48);
        tree.add(7);
        tree.add(124);
    }
}

```

#### Paso 2: Uso del método `last`

```java
   // Obtener el último elemento
    Integer lastElement = tree.last();

    // Imprimir el último elemento
    System.out.println("Último elemento: " + lastElement);
```

### Funcionamiento del método:

El método `last()` devuelve el último elemento del conjunto sin eliminarlo. En este caso, el último elemento será 200.

Resultado esperado:

```java
El último elemento es: 200
```

### Conclusión:

El método `last()` es útil para obtener el elemento más alto del conjunto sin eliminarlo.

### Nota adicional:

- Si el conjunto está vacío, `last()` lanzará una excepción NoSuchElementException, por lo que es importante asegurarse de que el conjunto contenga elementos antes de llamar a este método.
- No hay impacto en la estructura del árbol ya que el método solo devuelve el último elemento sin realizar ninguna modificación en el conjunto original.

## Método `lower(E e)`

## Método `pollFirst()`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación de TreeSet y agregar elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
    }
}
```

#### Paso 2: Uso del método `pollFirst()`

```java
Integer firstElement = treeSet.pollFirst();

// Imprimir el primer elemento (o null si el conjunto estaba vacío)
System.out.println("Primer elemento: " + firstElement);

```

### Funcionamiento del método:

El método pollFirst devuelve y elimina el primer elemento del conjunto. En este caso, dado que hemos agregado los números 5, 2, y 8, el primer elemento será 2.

Resultado esperado:

```
Primer elemento: 2
```

### Conclusión:

- El método pollFirst es útil para obtener y eliminar el elemento más bajo del conjunto.
- Devolverá null si el conjunto está vacío.

### Nota adicional:

Debido a que el elemento a eliminar con `pollFirst` siempre será el primer elemento ordenado, por lo tanto, este elemento
se encuentra en la hoja (leaf) del árbol. Al eliminar, no se necesitaria reorganizar todo el árbol, debido a que este
elemento se encuentra sin "hijos" por así decirlo.

## Método `pollLast()`

Duration: 00:01:00

### Paso a paso:

#### Paso 1: Creación de TreeSet y agregar elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
    }
}
```

#### Paso 2: Uso del método `pollLast()`

```java
Integer lastElement = treeSet.pollLast();

// Imprimir el último elemento (o null si el conjunto estaba vacío)
System.out.println("Último elemento: " + lastElement);
```

### Funcionamiento del método:

El método `pollLast` devuelve y elimina el último elemento del conjunto. En este caso, dado que hemos agregado los números 5, 2, y 8, el último elemento será 8.

```
Último elemento: 8
```

### Conclusión:

- El método pollLast es útil para obtener y eliminar el elemento más alto del conjunto.
- Devolverá null si el conjunto está vacío.

### Nota adicional:

Debido a que el elemento a eliminar con `pollLast` siempre será el último elemento ordenado, por lo tanto, este elemento
se encuentra en la hoja (leaf) del árbol. Al eliminar, no se necesitaria reorganizar todo el árbol, debido a que este
elemento se encuentra sin "hijos" por así decirlo.

## Método remove(Object o)

Duration: 00:02:00

### Paso a paso:

#### Paso 1: Creación de TreeSet y agregar elementos

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        // Crear un TreeSet
        TreeSet<Integer> treeSet = new TreeSet<>();

        // Agregar elementos al TreeSet
        treeSet.add(5);
        treeSet.add(2);
        treeSet.add(8);
    }
}
```

#### Paso 2: Uso del método `remove`

```java
boolean removed = treeSet.remove(2);

// Imprimir si el elemento fue eliminado
System.out.println("¿Se eliminó el elemento? " + removed);
```

### Funcionamiento del método:

El método remove elimina el elemento específico del conjunto. En este caso, al eliminar el número 2, el árbol se reorganizará adecuadamente.

Resultado esperado:

```
¿Se eliminó el elemento? true
```

#### Estado del árbol después de `remove(2)`

Antes de la eliminación:

![Tree initial with number](img/treeset-remove-1.png)

Después de la eliminación:

![Tree remove](img/treeset-remove-2.png)

### Caso especial: elemento a eliminar como root

Si el elemento a eliminar es la raíz, la reorganización del árbol puede afectar a sus subárboles. Por ejemplo, si eliminamos el 5:

Antes de la eliminación

![Tree initial with number](img/treeset-remove-1.png)

Después de la eliminación

![Tree initial with number](img/treeset-remove-3.png)

### Conclusión:

El método `remove` elimina el elemento específico del conjunto y reorganiza el árbol de búsqueda binaria en consecuencia.
