# Builder

El patrón de diseño Builder es un patrón creacional que se utiliza para crear objetos complejos paso a paso, permitiendo que el proceso de construcción pueda ser separado de la representación final del objeto. Esto significa que la misma construcción puede ser utilizada para crear diferentes representaciones del objeto.

En Rust, podemos implementar el patrón Builder utilizando un struct y un builder asociado. El struct representa el objeto que queremos construir y el builder es responsable de construirlo. El builder puede tener una serie de métodos que se encargan de establecer los valores de las propiedades del objeto a medida que se construye.

Aquí hay un ejemplo de cómo implementar el patrón Builder en Rust:

```rust
struct Person {
    name: String,
    age: u8,
    gender: Gender,
    address: String,
}

enum Gender {
    Male,
    Female,
}

struct PersonBuilder {
    name: Option<String>,
    age: Option<u8>,
    gender: Option<Gender>,
    address: Option<String>,
}

impl PersonBuilder {
    fn new() -> Self {
        PersonBuilder {
            name: None,
            age: None,
            gender: None,
            address: None,
        }
    }

    fn name(mut self, name: String) -> Self {
        self.name = Some(name);
        self
    }

    fn age(mut self, age: u8) -> Self {
        self.age = Some(age);
        self
    }

    fn gender(mut self, gender: Gender) -> Self {
        self.gender = Some(gender);
        self
    }

    fn address(mut self, address: String) -> Self {
        self.address = Some(address);
        self
    }

    fn build(self) -> Result<Person, String> {
        let name = self.name.ok_or("Name is required")?;
        let age = self.age.ok_or("Age is required")?;
        let gender = self.gender.ok_or("Gender is required")?;
        let address = self.address.ok_or("Address is required")?;

        Ok(Person {
            name,
            age,
            gender,
            address,
        })
    }
}

fn main() {
    let person = PersonBuilder::new()
        .name("John Doe".to_string())
        .age(30)
        .gender(Gender::Male)
        .address("123 Main St".to_string())
        .build()
        .unwrap();

    println!("{:?}", person);
}
```

En este ejemplo, `Person` es el objeto que queremos construir y `PersonBuilder` es el builder que se encarga de construirlo. `PersonBuilder` tiene una serie de métodos para establecer las propiedades del objeto, y también tiene un método `build` que construye el objeto y lo devuelve.

Los métodos del builder tienen el tipo `Self`, lo que significa que devuelven una referencia mutable al builder actual, lo que nos permite encadenar los métodos juntos para construir el objeto en una sola expresión.

El método `build` se encarga de comprobar que todas las propiedades necesarias han sido establecidas antes de construir el objeto. Si alguna propiedad falta, se devuelve un error. Si todas las propiedades están presentes, se construye el objeto y se devuelve un `Ok` que contiene el objeto construido.
