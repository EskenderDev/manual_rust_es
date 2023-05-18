# Crate

La palabra reservada `crate` en Rust se utiliza para hacer referencia al crate raíz o principal en el cual se encuentra el módulo actual. Un crate en Rust se refiere a un conjunto de archivos que se compilan juntos en una biblioteca o ejecutable.

Cuando se utiliza la palabra reservada `crate`, se hace referencia al crate actual, lo que puede ser útil para acceder a los elementos definidos en el crate principal desde otros módulos. Por ejemplo, si se tiene un archivo `main.rs` que es el punto de entrada de la aplicación, y se define un módulo en un archivo separado llamado `utils.rs`, se puede utilizar `crate` para hacer referencia a los elementos definidos en `main.rs`.

En otras palabras, `crate` es un mecanismo que permite a los módulos acceder a los elementos definidos en el crate raíz o principal sin tener que especificar el camino completo a través de los distintos módulos. Esto hace que sea más fácil reorganizar o refactorizar los módulos sin tener que cambiar todas las referencias a los elementos definidos en el crate principal.
