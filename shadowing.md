# Shadowing

El "ámbito" o "scope" en Rust se refiere al ámbito de visibilidad de una variable, es decir, el rango del programa en el que la variable es válida y se puede utilizar. El ámbito de una variable comienza en el punto en el que se declara y termina en el punto en el que sale de su alcance, que generalmente es cuando se cierra el bloque de código en el que se encuentra.

El sombreado ("shadowing") se refiere a la práctica de crear una nueva variable con el mismo nombre que una variable existente, lo que hace que la nueva variable "oculte" la anterior dentro del mismo ámbito. Esto se hace utilizando la palabra clave `let`, que permite redefinir una variable dentro de un nuevo ámbito de forma local sin modificar su valor original.

Por ejemplo:

```rust
let x = 5;         // Definimos una variable "x" en este ámbito
{
    let x = "hello";  // Definimos una nueva variable "x" dentro de este bloque interno, que oculta la variable "x" anterior
    println!("{}", x); // Imprime "hello"
}
println!("{}", x);    // Imprime "5", ya que la variable "x" original sigue siendo válida fuera del bloque interno
```

Es importante tener en cuenta que las variables sombreadas no afectan a la variable original, y que cada variable sombreada es una variable completamente nueva con su propio ámbito. Además, las variables sombreadas pueden tener un tipo diferente y un valor diferente que la variable original, lo que puede ser útil en ciertas situaciones.
