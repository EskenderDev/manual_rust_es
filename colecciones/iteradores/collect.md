# Collect

El método `collect()` se utiliza para convertir un iterador en una colección de datos, como un vector, un hash map, o incluso una cadena de caracteres.

El método `collect()` se utiliza típicamente después de haber generado un iterador de una fuente de datos (como un vector o un archivo) utilizando un método como `iter()`, `chars()`, o `lines()`. A continuación, se presenta un ejemplo simple de cómo utilizar el método `collect()`:

```css
cssCopy codelet numeros = vec![1, 2, 3, 4, 5];
let numeros_multiplicados: Vec<i32> = numeros.iter().map(|x| x * 2).collect();
```

En este ejemplo, el método `iter()` se utiliza para generar un iterador a partir del vector `numeros`. Luego, se utiliza el método `map()` para multiplicar cada número por 2 y se genera otro iterador. Finalmente, se utiliza el método `collect()` para convertir este iterador en un vector `numeros_multiplicados` que contiene los números originales multiplicados por 2.

El método `collect()` también se puede utilizar para generar otros tipos de colecciones de datos, como hash maps. Por ejemplo:

```rust
rustCopy codelet pares = vec![("a", 1), ("b", 2), ("c", 3)];
let hash_map: HashMap<&str, i32> = pares.into_iter().collect();
```

En este ejemplo, el método `into_iter()` se utiliza para generar un iterador a partir del vector `pares`. Luego, se utiliza el método `collect()` para convertir este iterador en un hash map `hash_map` que tiene las claves `"a"`, `"b"`, y `"c"` con los valores 1, 2, y 3, respectivamente.

En resumen, el método `collect()` es una herramienta poderosa para convertir iteradores en colecciones de datos de manera simple y eficiente.
