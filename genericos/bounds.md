# Bounds

Se refiere a las restricciones que se pueden colocar en los tipos genéricos. Las restricciones especifican los requisitos que deben cumplir los tipos genéricos para poder usarse en un contexto dado.

Los bounds se especifican utilizando la palabra clave "where" seguida de una o más restricciones. Por ejemplo, si queremos que un tipo genérico "T" tenga un método "foo", podemos especificar un bound así:

```rust
fn do_something<T: Foo>(x: T) {
    x.foo();
}
```

Aquí, "T: Foo" es el bound, lo que significa que "T" debe implementar el trait "Foo". También podemos especificar múltiples bounds separándolos con un signo "+".

```rust
fn do_something<T: Foo + Bar>(x: T) {
    x.foo();
    x.bar();
}
```

En este caso, "T" debe implementar tanto el trait "Foo" como el trait "Bar".

Podemos colocar restricciones en varios tipos de parámetros genéricos, incluyendo tipos de valores, tipos de referencia y tipos de punteros inteligentes.
