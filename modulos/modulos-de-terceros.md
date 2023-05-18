# Módulos de terceros

Para manejar módulos de terceros en Rust, se utiliza el sistema de gestión de paquetes de Rust llamado Cargo.

Para incluir un módulo de terceros en un proyecto, se debe agregar una dependencia al archivo `Cargo.toml`. En este archivo se especifica el nombre del paquete, la versión y el origen. Por ejemplo, para agregar la dependencia de la biblioteca `rand` se agrega lo siguiente al archivo `Cargo.toml`:

```
[dependencies]
rand = "0.8.4"
```

Luego de agregar la dependencia, se ejecuta el comando `cargo build` para descargar y compilar el paquete y sus dependencias. Después de esto, se puede utilizar el módulo importándolo en el archivo fuente con la palabra clave `use`. Por ejemplo, para usar el módulo `Rng` de la biblioteca `rand`, se puede hacer lo siguiente:

```rust
use rand::Rng;

fn main() {
    let mut rng = rand::thread_rng();
    let random_number = rng.gen_range(1..=100);
    println!("Random number: {}", random_number);
}
```

En este caso, la línea `use rand::Rng;` importa el módulo `Rng` de la biblioteca `rand` y permite utilizar el método `gen_range()` para generar un número aleatorio. La función `thread_rng()` crea un generador de números aleatorios en un hilo de ejecución separado.

En resumen, para manejar módulos de terceros en Rust se utilizan las dependencias de Cargo y la palabra clave `use` para importar los módulos necesarios en el archivo fuente.
