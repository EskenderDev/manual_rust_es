# macro\_rules!

`macro_rules!` es una macro de Rust que se utiliza para definir macros de compilación. Permite crear macros personalizadas que pueden manipular y transformar el código Rust antes de que se compile.

La sintaxis básica de `macro_rules!` es la siguiente:

```
macro_rules! mi_macro {
    (pat1) => {
        // código a ejecutar si se encuentra patrón 1
    };
    (pat2) => {
        // código a ejecutar si se encuentra patrón 2
    };
    // y así sucesivamente
}
```

La macro definida anteriormente se llama `mi_macro` y define dos patrones: `pat1` y `pat2`. Cuando la macro `mi_macro` se utiliza en el código Rust, el compilador buscará el patrón correspondiente y ejecutará el código correspondiente.

Por ejemplo, si se define una macro `repeat_expr` que repite una expresión n veces, se puede utilizar `macro_rules!` de la siguiente manera:

```
macro_rules! repeat_expr {
    ($expr:expr; $n:expr) => {
        {
            let mut result = Vec::new();
            for _ in 0..$n {
                result.push($expr);
            }
            result
        }
    };
}

fn main() {
    let repeated = repeat_expr!(2 + 2; 5);
    println!("{:?}", repeated); // Imprime "[4, 4, 4, 4, 4]"
}
```

En este ejemplo, la macro `repeat_expr` toma dos argumentos: una expresión y un número entero. La macro crea un vector que contiene $n$ copias de la expresión y devuelve el vector.



```
macro_rules! nombre_macro {
    (patrón1) => { expansión1 };
    (patrón2) => { expansión2 };
    // ...
    (patrónN) => { expansiónN };
}
```

Cada patrón está compuesto por uno o más fragmentos (identificadores precedidos por un signo `$`), que representan partes del código que coinciden con la sintaxis del patrón. Estos fragmentos pueden aparecer en la expansión de la macro utilizando el mismo nombre que se les asignó en el patrón.

Por ejemplo, la siguiente macro `vec!` se define utilizando `macro_rules!`:

```
macro_rules! vec {
    ($($x:expr),*) => {
        {
            let mut temp_vec = Vec::new();
            $(temp_vec.push($x);)*
            temp_vec
        }
    };
}
```

Esta macro se expande en un bloque de código que crea un `Vec` de Rust y lo inicializa con los valores dados. El patrón `$($x:expr),*` coincide con una lista separada por comas de expresiones arbitrarias, y la expansión se construye con un bucle que agrega cada expresión a un nuevo vector.

La ventaja de las macros `macro_rules!` es que pueden ser extremadamente generales y flexibles, permitiendo a los programadores escribir código muy expresivo. Sin embargo, también pueden ser muy difíciles de depurar, ya que el código que generan es completamente opaco para el compilador. Además, el hecho de que las macros no sean funciones reales significa que no pueden ser tipadas y, por lo tanto, no tienen información de tipo en tiempo de compilación.

En resumen, las macros `macro_rules!` son una herramienta poderosa en el kit de herramientas de un programador Rust, pero deben usarse con precaución y solo cuando son necesarias para lograr la expresividad deseada en el código.
