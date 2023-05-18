# Genéricos

Los genéricos permiten escribir código que funciona con diferentes tipos de datos sin tener que escribir una versión separada para cada tipo. Los genéricos se definen mediante la especificación de un parámetro de tipo en la definición de la función, estructura, enum, etc.

Por ejemplo, en lugar de escribir funciones separadas para sumar enteros, flotantes y otros tipos numéricos, podemos escribir una única función genérica que acepta cualquier tipo numérico que admita la operación de suma. Aquí hay un ejemplo:

```rust
fn suma<T>(a: T, b: T) -> T
where
    T: std::ops::Add<Output = T>,
{
    a + b
}

fn main() {
    let x = 5;
    let y = 6;
    let z = suma(x, y);
    println!("{}", z); // Imprime 11
}
```

En este ejemplo, la función `suma` utiliza un parámetro de tipo `T` que se especifica entre ángulos. La restricción `T: std::ops::Add<Output = T>` especifica que `T` debe implementar el operador de suma (`Add`) y que la salida debe ser del mismo tipo (`Output = T`). Esto garantiza que la función solo pueda sumar tipos que admitan la operación de suma y que devolverá un resultado del mismo tipo.

Los genéricos son una característica poderosa de Rust que permiten escribir código genérico y reutilizable. Sin embargo, a veces pueden complicar la sintaxis y hacer que el código sea más difícil de entender. Por lo tanto, es importante usar los genéricos de manera adecuada y en el momento adecuado para mantener el código claro y legible.
