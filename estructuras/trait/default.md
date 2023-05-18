# Default

El trait `Default` en Rust es una característica que permite establecer un valor predeterminado para un tipo. Este trait se utiliza para proporcionar un valor inicial o predeterminado para un tipo en caso de que no se especifique explícitamente.

El trait `Default` tiene un único método asociado llamado `default()`, que devuelve una instancia del tipo predeterminado. Este método se llama sin argumentos y se utiliza para crear una instancia del tipo con sus valores predeterminados.

Para que un tipo sea compatible con el trait `Default`, debe implementar el método `default()`. Esto se puede hacer manualmente o utilizando la derivación automática mediante la anotación `#[derive(Default)]`.

Aquí tienes un ejemplo de cómo utilizar el trait `Default`:

```rust
#[derive(Default)]
struct Person {
    name: String,
    age: u32,
    active: bool,
}

fn main() {
    // Crear una instancia de Person con los valores predeterminados
    let person: Person = Default::default();

    println!("Name: {}", person.name);
    println!("Age: {}", person.age);
    println!("Active: {}", person.active);
}
```

En este ejemplo, la estructura `Person` se deriva automáticamente del trait `Default` utilizando la anotación `#[derive(Default)]`. Esto permite llamar al método `default()` para crear una instancia de `Person` con sus valores predeterminados.

En el método `main()`, se crea una instancia de `Person` llamando a `Default::default()`. Los campos `name` y `age` se inicializan con los valores predeterminados para los tipos `String` y `u32`, respectivamente, mientras que el campo `active` se inicializa con el valor predeterminado para el tipo `bool` (que es `false`).

El trait `Default` es útil cuando deseas proporcionar un valor predeterminado para un tipo sin tener que especificarlo explícitamente en todas las instancias. También es común utilizar el trait `Default` junto con otros traits, como `Clone` y `PartialEq`, para proporcionar un comportamiento más completo para un tipo.
