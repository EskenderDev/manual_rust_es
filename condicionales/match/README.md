# Match

`match` es una estructura de control de flujo en Rust que se utiliza para comparar un valor con una serie de patrones y ejecutar el código correspondiente al patrón que coincida con el valor.

La sintaxis básica de `match` es la siguiente:

```
match value {
    pattern1 => {
        // hacer algo si value coincide con pattern1
    },
    pattern2 => {
        // hacer algo si value coincide con pattern2
    },
    _ => {
        // hacer algo si value no coincide con ningún patrón anterior
    }
}
```

En este ejemplo, `value` es el valor que se está comparando con los patrones. Los patrones son las opciones que se utilizan para hacer coincidir el valor. En este caso, el código dentro del bloque correspondiente al primer patrón que coincida con el valor se ejecutará. Si ningún patrón coincide con el valor, el código dentro del bloque `_` (el comodín) se ejecutará.

`match` es especialmente útil para manejar tipos de datos complejos como enumeraciones (enums) y tipos de estructuras (structs). Por ejemplo, considera el siguiente código:

```
enum Color {
    Red,
    Green,
    Blue,
}

fn main() {
    let color = Color::Red;

    match color {
        Color::Red => {
            println!("El color es rojo");
        },
        Color::Green => {
            println!("El color es verde");
        },
        Color::Blue => {
            println!("El color es azul");
        },
    }
}
```

En este ejemplo, la enumeración `Color` define tres valores posibles: `Red`, `Green` y `Blue`. La variable `color` se establece en `Color::Red`. El `match` se utiliza para comparar `color` con cada uno de los patrones en la enumeración `Color`. Como `color` es `Color::Red`, el primer bloque se ejecuta y se imprime "El color es rojo".

En resumen, `match` es una estructura de control de flujo poderosa y expresiva en Rust que permite manejar tipos de datos complejos y tomar decisiones basadas en el valor de una variable.
