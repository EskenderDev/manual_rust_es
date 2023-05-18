# Static Ref

`static ref` es una construcción en Rust que se utiliza para declarar una variable estática con una referencia inmutable. Esta sintaxis se utiliza específicamente cuando se desea declarar una variable estática que almacena una referencia a un valor.

La sintaxis de `static ref` se ve así:

```rust
static ref VARIABLE: TYPE = VALUE;
```

* `static` indica que la variable es estática, lo que significa que su duración es durante toda la vida útil del programa.
* `ref` indica que la variable almacenará una referencia en lugar del valor real.
* `VARIABLE` es el nombre de la variable estática.
* `TYPE` es el tipo de datos al que la referencia apunta.
* `VALUE` es el valor al que se realizará referencia.

Aquí hay un ejemplo para ilustrar cómo se usa `static ref`:

```rust
static ref DATA: Vec<u32> = vec![1, 2, 3, 4, 5];

fn main() {
    println!("{:?}", *DATA);
}
```

En este ejemplo, se declara una variable estática `DATA` que almacena una referencia inmutable a un `Vec<u32>`. La referencia está inicializada con un vector con algunos elementos. Luego, en la función `main()`, se imprime el contenido del vector accediendo a través de la referencia `*DATA`.

Es importante tener en cuenta que `static ref` se utiliza principalmente cuando se desea almacenar una referencia a un valor estático en lugar del valor real. Esto es útil en situaciones donde se desea compartir un valor inmutable entre diferentes partes del programa sin realizar copias innecesarias.
