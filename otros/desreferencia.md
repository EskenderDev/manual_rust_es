# Desreferencia

El operador de desreferenciación (`*`) se utiliza para acceder al valor al que apunta un puntero. Permite obtener el valor real al que apunta un puntero en lugar de manipular directamente el puntero en sí.

Existen dos situaciones principales en las que se utiliza el operador de desreferenciación:

1. Desreferenciación de punteros: Si tienes un puntero, puedes usar el operador `*` para acceder al valor al que apunta el puntero. Por ejemplo:

```rust
let x = 10;
let p = &x; // Puntero a la variable x
let y = *p; // Desreferenciación del puntero p para obtener el valor 10
println!("Valor de y: {}", y);
```

En este ejemplo, se crea un puntero `p` que apunta a la variable `x`. Al aplicar el operador de desreferenciación `*` sobre `p`, se obtiene el valor al que apunta el puntero, que en este caso es `10`. El valor se asigna a la variable `y` y se imprime su valor.

2. Desreferenciación de tipos inteligentes: En Rust, algunos tipos como `Box`, `Rc` y `Arc` se conocen como "punteros inteligentes" o "tipos de referencia inteligentes". Estos tipos contienen un puntero interno junto con metadatos adicionales y se utilizan para el manejo de la memoria. Al utilizar el operador de desreferenciación `*` en un puntero inteligente, se obtiene el valor contenido en el tipo inteligente. Por ejemplo:

```rust
use std::rc::Rc;

let x = Rc::new(5);
let y = *x; // Desreferenciación del puntero inteligente x para obtener el valor 5
println!("Valor de y: {}", y);
```

En este caso, se crea un puntero inteligente `x` utilizando `Rc`, que contiene el valor `5`. Al aplicar el operador de desreferenciación `*` sobre `x`, se obtiene el valor contenido en el puntero inteligente, que es `5`. El valor se asigna a la variable `y` y se imprime su valor.

Es importante tener en cuenta que el operador de desreferenciación solo se puede aplicar a punteros válidos y tipos inteligentes que admitan la operación de desreferenciación. En caso contrario, se producirá un error de compilación. Además, en Rust, el operador de desreferenciación también se utiliza para mutar valores a través de punteros mutables, utilizando `&mut`.
