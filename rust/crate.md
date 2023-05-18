# Crate

Un crate es una unidad de compilación que puede contener uno o varios módulos, y puede ser compilado como una biblioteca estática, una biblioteca dinámica o un binario ejecutable. Los crates son la forma en que Rust organiza y compila el código, y se pueden compartir y reutilizar fácilmente.

Hay dos tipos principales de crates en Rust: los crates de sistema y los crates externos. Los crates de sistema son las bibliotecas y herramientas que se incluyen con la instalación de Rust, mientras que los crates externos son bibliotecas y herramientas que se pueden instalar y utilizar desde el repositorio de crates de Rust, conocido como crates.io.

Cada crate en Rust tiene su propio ámbito de nombres, lo que significa que los identificadores dentro de un crate no entran en conflicto con los identificadores en otro crate. Esto ayuda a prevenir errores y simplifica la creación y el mantenimiento de grandes proyectos.

Los crates se definen en el archivo `Cargo.toml` en la raíz del proyecto. El archivo `Cargo.toml` especifica la información del paquete, como el nombre, la versión, las dependencias y la configuración de compilación. Para agregar una dependencia externa a un crate, se puede especificar el nombre de la dependencia y su versión en el archivo `Cargo.toml`, y luego ejecutar el comando `cargo build` para descargar e instalar la dependencia.

En resumen, los crates son una parte esencial de la organización y el desarrollo de proyectos en Rust, y permiten la creación de bibliotecas y herramientas compartibles y reutilizables.
