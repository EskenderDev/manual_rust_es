# Metodos

Los métodos son funciones que se definen dentro del contexto de una estructura o un tipo de datos, y se utilizan para realizar operaciones específicas en las instancias de ese tipo. Los métodos en Rust son similares a los métodos en otros lenguajes de programación orientados a objetos, pero con algunas características adicionales que son específicas de Rust.

Para definir un método en Rust, se utiliza la palabra clave `impl` (abreviatura de "implementación") seguida del nombre de la estructura o el tipo de datos al que se le desea agregar el método. A continuación, se define la función que se utilizará como el método, y se utiliza el nombre del tipo de datos seguido de `::` para indicar que es un método de ese tipo de datos. Los métodos también pueden tomar parámetros, y pueden acceder a los campos de la estructura o del tipo de datos utilizando la sintaxis de punto (`.`).

A continuación, se presenta un ejemplo de cómo definir un método en Rust para una estructura `Rectángulo` que calcula su área:

```
struct Rectangulo {
    ancho: f64,
    altura: f64,
}

impl Rectangulo {
    fn area(&self) -> f64 {
        self.ancho * self.altura
    }
}

fn main() {
    let rect = Rectangulo { ancho: 3.0, altura: 4.0 };

    println!("El área del rectángulo es {}", rect.area());
}
```

En este ejemplo, se define una estructura `Rectangulo` con dos campos: `ancho` y `altura`. Luego, se utiliza la palabra clave `impl` para definir un método `area` para la estructura `Rectangulo`. Este método toma una referencia `&self` a la instancia de la estructura y devuelve el producto de `ancho` y `altura`. En la función `main`, se crea una instancia de `Rectangulo` y se llama al método `area` utilizando la sintaxis de punto (`.`) para acceder al método.

En resumen, los métodos en Rust son funciones que se definen dentro del contexto de una estructura o un tipo de datos, y se utilizan para realizar operaciones específicas en las instancias de ese tipo. Para definir un método en Rust, se utiliza la palabra clave `impl` seguida del nombre de la estructura o el tipo de datos al que se le desea agregar el método, y se define la función que se utilizará como el método. Los métodos pueden tomar parámetros y acceder a los campos de la estructura o del tipo de datos utilizando la sintaxis de punto (`.`).
