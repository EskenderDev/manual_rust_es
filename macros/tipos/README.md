# Tipos



En Rust existen tres tipos de macros:

1. Macros de reglas (macro\_rules!): Es el tipo de macro más común en Rust y utiliza el sistema de patrones de Rust. Este tipo de macro se utiliza para crear macros de procesamiento de código más sencillas que realizan transformaciones sintácticas.
2. Macros procedurales: Este tipo de macro se introdujo en Rust 1.29 y permite definir macros que generan código a partir de un AST (Árbol de sintaxis abstracta) en tiempo de compilación. Las macros procedurales se definen con un atributo #\[proc\_macro] y pueden ser utilizadas en el código como si fueran funciones.
3. Macros de atributos: Las macros de atributos se utilizan para definir nuevos atributos que se pueden utilizar en el código. Estas macros se definen utilizando el atributo #\[attribute] y se utilizan para extender la sintaxis de Rust y permitir el uso de metadatos adicionales en el código.
