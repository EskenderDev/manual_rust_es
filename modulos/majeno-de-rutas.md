# Majeno de Rutas

Se refiere a la forma en que se especifica la ubicación de los archivos de código fuente y la organización de los módulos dentro de esos archivos.

La ruta de un módulo en Rust se especifica utilizando la sintaxis de puntos (`.`), donde cada punto representa un nivel adicional de anidamiento en la jerarquía de módulos. Por ejemplo, si se tiene un archivo `main.rs` y un archivo `utils.rs` en un directorio llamado `src`, y `utils.rs` contiene un módulo llamado `math`, la ruta completa del módulo sería `crate::utils::math`.

Además, Rust proporciona algunas palabras clave que se pueden utilizar para simplificar la especificación de rutas de módulos. La palabra clave `self` se refiere al módulo actual, mientras que la palabra clave `super` se refiere al módulo padre en la jerarquía de módulos. Por ejemplo, si se tiene un módulo llamado `math` dentro de un módulo llamado `utils`, se puede referir al módulo padre utilizando la ruta `super::`.

Para utilizar un módulo en Rust, se utiliza la palabra clave `mod`, seguida del nombre del módulo y la ruta de la ubicación del archivo de código fuente que lo contiene. Por ejemplo, si se tiene un archivo `utils.rs` que contiene un módulo llamado `math`, se puede utilizar la siguiente sintaxis para importar y utilizar ese módulo en otro archivo:

```
mod utils;
use utils::math;

fn main() {
    let result = math::add(2, 3);
    println!("{}", result);
}
```

En este ejemplo, `mod utils;` importa el archivo `utils.rs`, mientras que `use utils::math;` importa el módulo `math` dentro de ese archivo. Luego, se puede utilizar la función `add` del módulo `math` para realizar una operación matemática y mostrar el resultado en la salida estándar.
