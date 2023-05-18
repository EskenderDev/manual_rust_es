# Patrón Valor Literal

El patrón de valor literal en Rust permite hacer coincidir un valor concreto con una variable en una estructura de patrón. Por ejemplo, si tenemos una variable `x` de tipo `u32` que queremos hacer coincidir con el valor `42`, podemos hacerlo de la siguiente manera:

```rust
let x = 42;
match x {
    42 => println!("x es igual a 42"),
    _ => println!("x no es igual a 42"),
}
```

En este caso, el patrón `42` se utiliza para hacer coincidir el valor de `x` con el valor literal `42`. La variable `_` se utiliza como un comodín que coincide con cualquier valor que no haya sido coincidido por otro patrón.

También se pueden usar patrones de valor literal con cadenas de texto y caracteres, como en el siguiente ejemplo:

```rust
let s = "hola";
match s {
    "hola" => println!("La cadena es 'hola'"),
    _ => println!("La cadena no es 'hola'"),
}

let c = 'x';
match c {
    'x' => println!("El caracter es 'x'"),
    _ => println!("El caracter no es 'x'"),
}
```

En ambos casos, el patrón de valor literal se utiliza para hacer coincidir la variable `s` o `c` con una cadena de texto o un caracter específico.
