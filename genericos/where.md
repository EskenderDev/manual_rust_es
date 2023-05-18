# Where

where es una palabra clave utilizada para imponer restricciones adicionales en los tipos genéricos en una función, un trait o una implementación de un trait. Esto ayuda a hacer que el código sea más legible y fácil de entender al declarar las restricciones en una sección separada y no mezcladas con la declaración de tipos genéricos.

Por ejemplo, supongamos que tenemos un trait llamado `Printable` que define un método `print(&self)` que imprime el objeto en la consola. Ahora, queremos implementar una función genérica que toma un objeto y lo imprime utilizando el método `print()` del trait `Printable`, pero queremos limitar esta función sólo a aquellos tipos que implementan `Printable`. Podemos hacerlo utilizando la cláusula `where` de la siguiente manera:

```rust
trait Printable {
    fn print(&self);
}

fn print_object<T>(obj: &T)
    where T: Printable
{
    obj.print();
}

struct Dog {
    name: String,
}

impl Printable for Dog {
    fn print(&self) {
        println!("Dog named {}", self.name);
    }
}

fn main() {
    let d = Dog { name: String::from("Rusty") };
    print_object(&d);
}
```

En este ejemplo, hemos definido un `trait` llamado `Printable` y una función genérica llamada `print_object()` que toma una referencia a un objeto genérico `T`. Pero, a través de la cláusula `where`, hemos impuesto una restricción adicional en el tipo `T` que dice que sólo aquellos tipos que implementan el trait `Printable` pueden ser utilizados con esta función. Hemos implementado el trait `Printable` para el struct `Dog`, y en `main()` hemos creado una instancia de `Dog` y llamado a la función `print_object()` con ella.

La cláusula `where` también se puede utilizar en las definiciones de los traits y en las implementaciones de los mismos, para imponer restricciones adicionales en los tipos genéricos que se utilizan en los métodos y funciones asociados a esos traits. En general, la cláusula `where` es una herramienta útil para hacer que el código sea más legible y fácil de entender al declarar las restricciones en una sección separada y no mezcladas con la declaración de tipos genéricos.
