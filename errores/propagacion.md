# Propagación

La propagación de errores en Rust se refiere a la forma en que se manejan y transmiten los errores a través de las funciones. Rust proporciona mecanismos para manejar errores de manera explícita y garantizar la seguridad y la ausencia de errores en tiempo de ejecución.

En Rust, el tipo `Result<T, E>` se utiliza comúnmente para manejar errores. Un `Result` puede tener uno de dos valores posibles: `Ok(T)`, que indica que la operación fue exitosa y contiene un valor de tipo `T`, o `Err(E)`, que indica que ocurrió un error y contiene información sobre el error de tipo `E`.

Cuando una función produce un `Result`, puedes utilizar el operador `?` para propagar automáticamente el error hacia arriba en la cadena de llamadas de funciones. Si se encuentra un `Err` en algún punto, se detendrá la ejecución de la función actual y el `Err` se devolverá como resultado a la función que la llamó. Esto permite que los errores se propaguen a través de las funciones de manera eficiente y concisa.

Aquí tienes un ejemplo que muestra cómo se puede utilizar la propagación de errores con el operador `?`:

```rust
use std::fs::File;
use std::io::Read;

fn read_file_contents(file_path: &str) -> Result<String, std::io::Error> {
    let mut file = File::open(file_path)?; // Intenta abrir el archivo

    let mut contents = String::new();
    file.read_to_string(&mut contents)?; // Intenta leer el contenido del archivo

    Ok(contents) // Devuelve el contenido como Ok si todo fue exitoso
}

fn main() {
    let file_path = "example.txt";
    match read_file_contents(file_path) {
        Ok(contents) => println!("Contenido del archivo:\n{}", contents),
        Err(error) => println!("Error al leer el archivo: {}", error),
    }
}
```

En este ejemplo, la función `read_file_contents` intenta abrir un archivo y leer su contenido. Si ocurre algún error durante la apertura del archivo o la lectura de su contenido, se propagará automáticamente como un `Err` y se imprimirá en la función `main` utilizando el patrón `match`.

Al utilizar el operador `?` después de las operaciones que pueden devolver un `Result`, Rust se encarga de manejar los errores de manera eficiente y proporciona un código más legible y conciso para el manejo de errores.

Es importante tener en cuenta que la propagación de errores con el operador `?` solo se puede utilizar en funciones que devuelven un `Result` o en funciones que se llaman desde una función que devuelve un `Result`. Además, el tipo de error devuelto por todas las operaciones con `?` debe ser el mismo o convertible entre sí.
