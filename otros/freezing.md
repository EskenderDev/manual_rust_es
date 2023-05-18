# Freezing

En Rust, "freezing" se refiere a la práctica de hacer que un valor sea inmutable, es decir, que no pueda ser modificado una vez que se ha creado. Rust tiene un sistema de control de mutabilidad muy fuerte que ayuda a prevenir errores y bugs en el código, y una de las formas en que se logra esto es mediante la congelación de valores.

La congelación de valores se logra utilizando la palabra clave `mut` para especificar que una variable es mutable o utilizando la palabra clave `const` para especificar que una variable es inmutable. La diferencia entre `mut` y `const` es que `mut` permite la modificación de la variable, mientras que `const` no lo hace.

Por ejemplo, se puede crear una variable inmutable de la siguiente manera:

```rust
const PI: f32 = 3.14159;
```

En este caso, `PI` es una variable constante que no puede ser modificada una vez que se ha definido. En contraste, se puede crear una variable mutable de la siguiente manera:

```rust
let mut x = 5;
x = 10; // Se puede modificar el valor de "x" porque se ha declarado como mutable
```

En general, se recomienda utilizar variables inmutables siempre que sea posible, ya que esto ayuda a prevenir errores y bugs en el código. Sin embargo, en algunos casos puede ser necesario utilizar variables mutables, por ejemplo, cuando se trabaja con datos que cambian con el tiempo.
