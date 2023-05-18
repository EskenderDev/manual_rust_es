# Sistema de Patrones

El sistema de patrones en Rust se refiere a la capacidad del lenguaje para realizar coincidencias de patrones en varias estructuras de datos, incluyendo tuplas, enums, structs y tipos de referencia. Esto permite escribir código más expresivo y conciso al realizar diferentes acciones según la forma o contenido de un valor.

Los patrones se utilizan principalmente en dos situaciones: en el contexto de la declaración de variables y en el contexto del control de flujo, como en las expresiones `match` y `if let`.

En la declaración de variables, se puede utilizar un patrón para asignar valores a una o varias variables al mismo tiempo. Por ejemplo, se podría usar un patrón de tupla para asignar valores a varias variables de una sola vez:

```
let tupla = (1, 2, 3);
let (a, b, c) = tupla;
```

En este caso, el patrón `(a, b, c)` se utiliza para asignar los valores 1, 2 y 3 a las variables `a`, `b` y `c`, respectivamente.

En el control de flujo, los patrones se utilizan en las expresiones `match` y `if let` para comparar un valor con uno o varios patrones. Por ejemplo, en el siguiente código se utiliza un patrón de enum para determinar qué acción tomar en función del valor de la variable `opción`:

```
enum Opcion {
    Uno,
    Dos(i32),
    Tres { x: i32, y: i32 },
}

let opción = Opcion::Dos(42);

match opción {
    Opcion::Uno => println!("Uno"),
    Opcion::Dos(valor) => println!("Dos: {}", valor),
    Opcion::Tres { x, y } => println!("Tres: {} {}", x, y),
}
```

En este caso, el patrón `Opcion::Dos(valor)` se utiliza para imprimir el valor de la opción si es del tipo `Dos`, y el patrón `Opcion::Tres { x, y }` se utiliza para imprimir los valores `x` e `y` si es del tipo `Tres`.

Además de los patrones básicos, Rust también admite patrones más avanzados, como patrones de rango, patrones de referencia y patrones de desestructuración. Estos patrones permiten realizar coincidencias más específicas y detalladas en los valores de datos.
