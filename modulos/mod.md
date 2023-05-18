# Mod

Los módulos en Rust son una forma de organizar y estructurar el código en unidades lógicas y separadas. Un módulo es un contenedor para funciones, tipos, constantes, y otros elementos relacionados con una funcionalidad específica.

La sintaxis para definir un módulo es:

```rust
mod nombre_modulo {
    // Contenido del módulo
}
```

El contenido del módulo puede incluir funciones, tipos, constantes, y otros elementos, y se accede a ellos usando la sintaxis de punto, similar a la de la estructura:

```rust
nombre_modulo::nombre_elemento
```

Los módulos también pueden tener submódulos, que se definen dentro del módulo padre:

```rust
mod nombre_modulo {
    mod submodulo {
        // Contenido del submódulo
    }
}
```

Para usar un módulo en otro archivo, primero debemos definir el módulo en el archivo original. Luego, podemos importar ese módulo en el nuevo archivo usando la palabra clave `use`:

```rust
// En archivo1.rs
mod nombre_modulo {
    // Contenido del módulo
}

// En archivo2.rs
use crate::nombre_modulo;
```

Podemos usar la sintaxis de punto para acceder a los elementos del módulo importado:

```rust
nombre_modulo::nombre_elemento
```

Además, los módulos también pueden ser definidos en archivos separados y organizados en una jerarquía de directorios. En este caso, debemos usar la palabra clave `mod` seguida del nombre del archivo, sin la extensión `.rs`. Por ejemplo, si tenemos un archivo `mi_modulo.rs` en un directorio llamado `src/modulos`, podemos definir el módulo de la siguiente manera:

```rust
mod modulos;
```

Esto buscará el archivo `mi_modulo.rs` en el directorio `src/modulos` y cargará el contenido del archivo como un módulo. Luego podemos acceder a los elementos del módulo usando la sintaxis de punto, como se mencionó anteriormente.
