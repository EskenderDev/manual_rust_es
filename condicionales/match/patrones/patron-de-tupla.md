# Patron de tupla

Un patrón de tupla es una forma de desestructurar una tupla y extraer sus valores. A continuación se muestran algunos ejemplos de patrones de tuplas:

Ejemplo 1: desestructuración de una tupla en dos variables

```
let tupla = (42, "Hola mundo");
let (x, y) = tupla;

println!("x es igual a {}", x); // salida: x es igual a 42
println!("y es igual a {}", y); // salida: y es igual a Hola mundo
```

En este ejemplo, la tupla `(42, "Hola mundo")` se asigna a la variable `tupla`. Luego, se desestructura la tupla en las variables `x` e `y`. El valor `42` se asigna a la variable `x` y `"Hola mundo"` se asigna a la variable `y`.

Ejemplo 2: desestructuración de una tupla en variables y un patrón de wildcard

```
let tupla = (42, "Hola mundo");
let (x, _) = tupla;

println!("x es igual a {}", x); // salida: x es igual a 42
```

En este ejemplo, la tupla `(42, "Hola mundo")` se asigna a la variable `tupla`. Luego, se desestructura la tupla en la variable `x` y un patrón de wildcard `_`. El valor `42` se asigna a la variable `x`, pero como no se proporciona una variable para el segundo elemento de la tupla, el patrón de wildcard `_` se utiliza para ignorarlo.

Ejemplo 3: desestructuración de una tupla en variables y un patrón de rango

```
let tupla = (42, "Hola mundo");
let (x, texto) = tupla;

match texto {
    "Hola".."Hola mundo" => println!("El texto coincide con el patrón"),
    _ => println!("El texto no coincide con el patrón")
}
```

En este ejemplo, la tupla `(42, "Hola mundo")` se asigna a la variable `tupla`. Luego, se desestructura la tupla en las variables `x` y `texto`. El valor `42` se asigna a la variable `x` y `"Hola mundo"` se asigna a la variable `texto`. A continuación, se utiliza una estructura `match` para comparar el valor de la variable `texto` con un patrón de rango `"Hola".."Hola mundo"`. Si el valor de la variable `texto` está en ese rango, se imprimirá "El texto coincide con el patrón". De lo contrario, se imprimirá "El texto no coincide con el patrón".
