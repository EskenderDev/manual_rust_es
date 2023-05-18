# Iteradores

Los iteradores son una herramienta poderosa para trabajar con colecciones de datos de manera flexible y eficiente. Los iteradores son objetos que producen una secuencia de valores a partir de una fuente de datos (como un vector, un hash map, o un archivo), y permiten realizar operaciones como filtrado, mapeo, y reducción de los valores producidos.

En Rust, los iteradores se definen como un conjunto de métodos que se implementan en cualquier tipo que se puede recorrer de forma secuencial. Los iteradores se crean mediante la llamada al método `iter()` en un tipo iterable, y pueden ser transformados mediante el uso de métodos como `map()`, `filter()`, `take()`, y `skip()`, entre otros. Algunos de los métodos más comunes que se utilizan con los iteradores en Rust incluyen:

* `map()`: Crea un nuevo iterador aplicando una función a cada valor producido por el iterador original.
* `filter()`: Crea un nuevo iterador que produce solo los valores que cumplen con una determinada condición.
* `take()`: Crea un nuevo iterador que produce solo un número determinado de valores del iterador original.
* `skip()`: Crea un nuevo iterador que omite un número determinado de valores del iterador original.
* `fold()`: Reduce los valores producidos por el iterador a un solo valor, utilizando una función que acumula los valores.
* `collect()`: Convierte los valores producidos por el iterador en una colección de datos.

A continuación se presenta un ejemplo simple de cómo utilizar un iterador en Rust:

```
let numeros = vec![1, 2, 3, 4, 5];
let numeros_pares: Vec<i32> = numeros.iter().filter(|x| x % 2 == 0).map(|x| x * 2).collect();
```

En este ejemplo, el método `iter()` se utiliza para generar un iterador a partir del vector `numeros`. Luego, se utiliza el método `filter()` para filtrar solo los valores pares, y el método `map()` para multiplicar cada número por 2 y generar otro iterador. Finalmente, se utiliza el método `collect()` para convertir este iterador en un vector `numeros_pares` que contiene los números pares originales multiplicados por 2.

En resumen, los iteradores son una herramienta poderosa para trabajar con colecciones de datos en Rust, y permiten realizar operaciones de manera flexible y eficiente. La documentación oficial de Rust proporciona más información y ejemplos detallados sobre cómo utilizar los iteradores en diferentes situaciones.
