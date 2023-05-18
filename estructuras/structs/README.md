# Structs

Las estructuras (también conocidas como "structs") son un tipo de datos personalizado que se utiliza para agrupar valores relacionados juntos en una sola entidad. Las estructuras en Rust son similares a las estructuras en otros lenguajes de programación, como C y C++, pero con algunas características adicionales que son específicas de Rust.

Las estructuras en Rust se definen utilizando la palabra clave `struct`, seguida del nombre de la estructura y una lista de campos que componen la estructura. Cada campo tiene un nombre y un tipo, y se separa de los otros campos con una coma. A continuación se presenta un ejemplo simple de cómo definir una estructura en Rust:

```
struct Persona {
    nombre: String,
    edad: u32,
    altura: f64,
}
```

En este ejemplo, se define una estructura llamada `Persona` con tres campos: `nombre` (un `String`), `edad` (un entero sin signo de 32 bits), y `altura` (un número de coma flotante de 64 bits).

Una vez que se ha definido una estructura, se pueden crear instancias de la estructura mediante la llamada a su nombre y proporcionando valores para cada uno de los campos. A continuación se presenta un ejemplo de cómo crear una instancia de la estructura `Persona`:

```
let persona1 = Persona {
    nombre: String::from("Juan"),
    edad: 30,
    altura: 1.75,
};
```

En este ejemplo, se crea una instancia de la estructura `Persona` llamada `persona1`, con los valores `nombre` "Juan", `edad` 30, y `altura` 1.75.

Una vez que se ha creado una instancia de la estructura, se pueden acceder a los valores de sus campos utilizando la sintaxis de punto (`.`). A continuación se presenta un ejemplo de cómo acceder a los valores de los campos de una instancia de la estructura `Persona`:

```
println!("El nombre de la persona es {}", persona1.nombre);
println!("La edad de la persona es {}", persona1.edad);
println!("La altura de la persona es {}", persona1.altura);
```

En resumen, las estructuras en Rust son un tipo de datos personalizado que se utiliza para agrupar valores relacionados juntos en una sola entidad. Las estructuras en Rust se definen utilizando la palabra clave `struct`, seguida del nombre de la estructura y una lista de campos que componen la estructura. Una vez que se ha definido una estructura, se pueden crear instancias de la estructura y acceder a los valores de sus campos utilizando la sintaxis de punto (`.`).
