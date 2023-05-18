# Copy, Clone

En Rust, existen dos formas principales de duplicar o clonar valores: la clonación y la copia.

1. Clonación (`Clone`): La clonación es el proceso de crear una nueva instancia de un valor copiando todos sus datos. Para que un tipo sea clonable, debe implementar el trait `Clone`. La clonación se realiza explícitamente llamando al método `clone()` en una instancia del tipo clonable. La clonación crea una copia independiente del valor original, lo que significa que ambos valores tienen su propia asignación de memoria y no comparten referencias o datos internos. La clonación se utiliza cuando se necesita crear una copia profunda de un valor y se quiere mantener la propiedad exclusiva de los datos.

Ejemplo de clonación:

```rust
#[derive(Clone)]
struct Persona {
    nombre: String,
    edad: u32,
}

let persona1 = Persona {
    nombre: String::from("Alice"),
    edad: 30,
};

let persona2 = persona1.clone();
```

En este ejemplo, `persona1` se clona en `persona2`, creando una nueva instancia de `Persona` con los mismos valores. Ambas instancias son independientes y pueden modificarse por separado.

2. Copia (`Copy`): La copia es una característica especial que tienen algunos tipos en Rust que permiten duplicar valores automáticamente sin la necesidad de llamar explícitamente a un método de clonación. Los tipos que implementan el trait `Copy` son aquellos cuyos valores se pueden copiar de manera superficial y no requieren recursos adicionales para duplicarse, como enteros, booleanos y otros tipos primitivos. La copia se realiza automáticamente cuando asignas o pasas un valor a otra variable. La copia no realiza una copia profunda, sino que simplemente duplica los bits en memoria del valor original.

Ejemplo de copia:

```rust
let x = 5;
let y = x; // Se realiza una copia automática

println!("x: {}", x); // Imprime "x: 5"
println!("y: {}", y); // Imprime "y: 5"
```

En este ejemplo, el valor de `x` se copia en `y` de forma automática. Ambas variables contienen su propia copia del valor `5`, y modificar `y` no afectará a `x` y viceversa.

En resumen, la clonación se utiliza cuando se necesita una copia profunda de un valor y se quiere mantener la propiedad exclusiva de los datos, mientras que la copia se utiliza para tipos que implementan `Copy` y permiten duplicar automáticamente los valores sin realizar una copia profunda.
