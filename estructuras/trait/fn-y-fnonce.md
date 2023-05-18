# Fn y FnOnce

En Rust, `Fn` y `FnOnce` son traits utilizados para representar diferentes tipos de funciones o clausuras.

El trait `Fn`

* El trait `Fn` se utiliza para representar funciones o clausuras que pueden ser llamadas de forma inmutable (sin modificar el estado de las variables capturadas). Esto significa que se pueden invocar múltiples veces y se les permite acceder a las variables inmutables que han capturado.

El trait `FnOnce`

* El trait `FnOnce` se utiliza para representar funciones o clausuras que pueden ser llamadas una vez y consumen los recursos que han capturado. Estas funciones o clausuras toman la propiedad (ownership) de las variables capturadas y no pueden ser invocadas nuevamente.

Ambos traits, `Fn` y `FnOnce`, son parte del mecanismo de trait en Rust y se utilizan para proporcionar una interfaz común para trabajar con diferentes tipos de funciones o clausuras. Esto permite que se traten de manera genérica y se utilicen en contextos polimórficos.

Aquí hay un ejemplo para ilustrar la diferencia entre `Fn` y `FnOnce`:

```rust
fn call_twice<F: Fn(i32)>(f: F) {
    for i in 0..2 {
        f(i);
    }
}

fn call_once<F: FnOnce()>(f: F) {
    f();
}

fn main() {
    let message = "Hello";

    // Uso de Fn
    call_twice(|num| println!("{} World {}", message, num));

    // Uso de FnOnce
    call_once(move || println!("{} World!", message));

    // Esto daría un error porque la clausura se ha consumido en la llamada anterior
    // call_once(move || println!("{} World!", message));
}
```

En este ejemplo, `call_twice` acepta una función o clausura que implementa el trait `Fn`. Se puede llamar dos veces sin problemas y acceder a las variables capturadas de forma inmutable.

Por otro lado, `call_once` acepta una función o clausura que implementa el trait `FnOnce`. Esta función o clausura se consume en la primera llamada y no se puede invocar nuevamente.

Es importante tener en cuenta que el uso de `Fn` y `FnOnce` depende del contexto y los requisitos específicos de tu programa. Debes elegir el trait apropiado en función de si la función o clausura necesita ser llamada múltiples veces o solo una vez y si necesita acceder a las variables de forma inmutable o consumirlas.
