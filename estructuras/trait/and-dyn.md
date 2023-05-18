# \&dyn

`&dyn` se utiliza para crear una referencia a un tipo que implementa un trait en particular. Esto es útil cuando se quiere almacenar una referencia a un objeto que implementa un trait en una estructura de datos, por ejemplo.

Por ejemplo, supongamos que tenemos un trait llamado `Animal` que define un método `sound()` que devuelve un `String`. Podemos crear una referencia a un objeto que implementa este trait de la siguiente manera:

```rust
trait Animal {
    fn sound(&self) -> String;
}

struct Dog {
    name: String,
}

impl Animal for Dog {
    fn sound(&self) -> String {
        return format!("{} says woof!", self.name);
    }
}

fn main() {
    let d = Dog { name: String::from("Rusty") };
    let animal_ref: &dyn Animal = &d;
    println!("{}", animal_ref.sound());
}
```

En este ejemplo, hemos definido un `struct` llamado `Dog` y hemos implementado el trait `Animal` para ese struct. Luego, en `main()`, creamos una instancia de `Dog` llamada `d` y creamos una referencia `animal_ref` a ella utilizando `&dyn Animal`. Finalmente, llamamos al método `sound()` a través de la referencia `animal_ref`.

El uso de `&dyn` permite crear una referencia a un objeto que implementa un trait sin conocer el tipo exacto del objeto en tiempo de compilación. Esto es útil cuando se quiere trabajar con tipos genéricos que pueden implementar diferentes traits.
