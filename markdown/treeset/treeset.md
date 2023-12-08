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

## Método `floor?(E e)`

## Método `headSet(Object toElement)`

## Método `higher(E e)`

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