# Macros de Atributo

Las macros con `#[ ]` se conocen como atributos de macro y se usan para anotar elementos del código que las macros expanden. Los atributos de macro proporcionan información adicional al compilador sobre cómo se debe procesar un elemento en particular.

Por ejemplo, el atributo de macro `#[derive]` se usa para generar automáticamente el código de implementación de ciertos traits para una estructura o enum en Rust. Otro ejemplo es el atributo de macro `#[allow(dead_code)]`, que se usa para indicar al compilador que permita la existencia de funciones no utilizadas en el código.

Para definir un atributo de macro, se coloca el atributo precedido por un símbolo `#` justo antes de un elemento que lo sigue. A continuación, se proporciona la definición del atributo de macro, que puede tomar la forma de una sola palabra o un conjunto de argumentos separados por comas entre paréntesis.

Por ejemplo, la siguiente es una definición de atributo de macro que se llama `my_attribute` y que toma un argumento:

```rust
macro_rules! my_attribute {
    ($arg:expr) => {
        // implementación del atributo de macro aquí
    };
}
```

Luego, el atributo de macro se puede usar para anotar cualquier elemento del código que lo siga, como se muestra en el siguiente ejemplo:

```rust
#[my_attribute("argument value")]
fn my_function() {
    // cuerpo de la función aquí
}
```

En este ejemplo, la función `my_function` está anotada con el atributo de macro `my_attribute`, y se proporciona un argumento para el atributo en forma de cadena de texto.
