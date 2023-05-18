# Patrones avanzados

Los patrones avanzados son una forma más sofisticada y poderosa de hacer coincidir patrones en Rust. Aquí hay algunos ejemplos de patrones avanzados:

1.  Patrones con guardas: permiten agregar una expresión booleana que debe ser verdadera para que el patrón coincida. Esto se logra mediante la palabra clave `if` seguida de una expresión booleana entre paréntesis. Por ejemplo:

    ```rust
    match x {
        Some(y) if y > 5 => println!("y es mayor que 5"),
        Some(y) if y < 5 => println!("y es menor que 5"),
        _ => println!("No hay valor"),
    }
    ```
2.  Patrones con variables atómicas: permiten descomponer un valor en sus partes constituyentes y vincularlas a variables. Esto se logra mediante la sintaxis `@`. Por ejemplo:

    ```rust
    match (1, 2) {
        (x, y) if x < 5 && y < 5 => println!("Ambos números son menores que 5"),
        (x @ 1..=5, y @ 1..=5) => println!("{} y {} están en el rango de 1 a 5", x, y),
        _ => println!("No hay valor"),
    }
    ```
3.  Patrones con variables ligadas: permiten vincular una variable a un valor que se coincide con el patrón y luego usar esa variable en el cuerpo del `match`. Esto se logra mediante la sintaxis `@`. Por ejemplo:

    ```rust
    match Some(42) {
        Some(x) => println!("El valor es {}", x),
        None => println!("No hay valor"),
    }
    ```
4.  Patrones con variables ignoradas: permiten ignorar partes de un valor que no se necesitan en el cuerpo del `match`. Esto se logra mediante la sintaxis `_`. Por ejemplo:

    ```rust
    match (1, 2, 3) {
        (_, _, z) => println!("El tercer valor es {}", z),
        _ => println!("No hay valor"),
    }
    ```
5.  Patrones con desestructuración: permiten descomponer valores complejos en sus partes constituyentes y hacer coincidir patrones en cada parte. Esto se logra mediante la sintaxis `..` o `...`. Por ejemplo:

    ```rust
    struct Persona {
        nombre: String,
        edad: u8,
    }

    let persona = Persona { nombre: String::from("Juan"), edad: 30 };

    match persona {
        Persona { nombre, .. } => println!("El nombre es {}", nombre),
        Persona { nombre, edad: 18..=35 } => println!("{} tiene entre 18 y 35 años", nombre),
        _ => println!("No hay valor"),
    }
    ```

Estos son solo algunos ejemplos de patrones avanzados en Rust. Los patrones son una herramienta poderosa y versátil que permite escribir código conciso y expresivo.
