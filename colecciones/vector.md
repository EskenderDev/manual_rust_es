# Vector

Un vector en Rust es una colección ordenada de elementos del mismo tipo, que se puede cambiar en tamaño dinámicamente. Es decir, un vector es un tipo de dato que permite almacenar múltiples valores en una única estructura de datos.

En Rust, un vector se define utilizando la estructura `Vec<T>`, donde `T` es el tipo de dato que se almacenará en el vector. Por ejemplo, para crear un vector de enteros que contenga los números del 1 al 5, se podría escribir:

```
let v = vec![1, 2, 3, 4, 5];
```

Los elementos del vector se pueden acceder mediante un índice numérico, empezando desde cero. Por ejemplo, para acceder al segundo elemento del vector `v`, se podría escribir:

```
let segundo_elemento = v[1];
```

También es posible añadir nuevos elementos al vector utilizando el método `push`, o eliminar elementos utilizando el método `pop`. Por ejemplo, para añadir un nuevo número al final del vector `v`, se podría escribir:

```
v.push(6);
```

Y para eliminar el último elemento del vector, se podría escribir:

```
v.pop();
```

Los vectores en Rust son muy útiles para almacenar colecciones de datos que pueden crecer o reducir en tamaño dinámicamente, y se utilizan con frecuencia en muchos programas y bibliotecas de Rust.

### Métodos básicos de un vector

* `new() -> Vec<T>`: Crea un nuevo vector vacío.
* `with_capacity(capacity: usize) -> Vec<T>`: Crea un nuevo vector con capacidad preasignada para almacenar un número determinado de elementos.
* `len(&self) -> usize`: Devuelve el número de elementos actualmente almacenados en el vector.
* `is_empty(&self) -> bool`: Devuelve `true` si el vector está vacío, y `false` en caso contrario.
* `capacity(&self) -> usize`: Devuelve la capacidad actual del vector.
* `reserve(&mut self, additional: usize)`: Reserva capacidad adicional en el vector para poder almacenar un número determinado de elementos sin tener que asignar más memoria.
* `shrink_to_fit(&mut self)`: Reduce la capacidad del vector al número de elementos que actualmente contiene.
* `truncate(&mut self, len: usize)`: Trunca el vector al número de elementos especificado.

### Métodos para añadir y eliminar elementos

* `push(&mut self, value: T)`: Añade un elemento al final del vector.
* `pop(&mut self) -> Option<T>`: Elimina y devuelve el último elemento del vector, o devuelve `None` si el vector está vacío.
* `insert(&mut self, index: usize, element: T)`: Inserta un elemento en una posición específica del vector, desplazando los demás elementos hacia la derecha.
* `remove(&mut self, index: usize) -> T`: Elimina y devuelve el elemento en una posición específica del vector, desplazando los demás elementos hacia la izquierda.

### Métodos para acceder y modificar elementos

* `get(&self, index: usize) -> Option<&T>`: Devuelve una referencia al elemento en una posición específica del vector, o devuelve `None` si la posición está fuera de los límites del vector.
* `get_mut(&mut self, index: usize) -> Option<&mut T>`: Devuelve una referencia mutable al elemento en una posición específica del vector, o devuelve `None` si la posición está fuera de los límites del vector.
* `iter(&self) -> Iter<T>`: Devuelve un iterador inmutable que permite recorrer todos los elementos del vector.
* `iter_mut(&mut self) -> IterMut<T>`: Devuelve un iterador mutable que permite recorrer y modificar todos los elementos del vector.

### Métodos de utilidad

* `sort(&mut self)`: Ordena los elementos del vector en orden ascendente.
* `sort_by<F>(&mut self, compare: F)`: Ordena los elementos del vector utilizando una función de comparación personalizada.
* `reverse(&mut self)`: Invierte el orden de los elementos del vector.
* `clone(&self) -> Vec<T>`: Crea una copia profunda del vector.
* `as_slice(&self) -> &[T]`: Devuelve una referencia inmutable al vector como una rebanada (slice) del tipo `[T]`.
* `as_mut_slice(&mut self) -> &mut [T]`: Devuelve una referencia mutable al vector como una rebanada (slice) del tipo `&mut [T]`.
