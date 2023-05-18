# String

La estructura `String` se utiliza para representar una cadena de caracteres como un objeto en la memoria. Al ser una estructura, permite trabajar con cadenas de caracteres de forma más flexible y realizar operaciones como concatenación, división, búsqueda, etc.

Aquí hay algunos ejemplos de cómo trabajar con `String` en Rust:

1.  Crear una cadena de caracteres:

    ```
    let mut s = String::new();  // Crear una cadena vacía
    let s = String::from("Hola mundo");  // Crear una cadena a partir de un string literal
    let s = "Hola mundo".to_string();  // Crear una cadena a partir de un string literal utilizando el método to_string()
    ```
2.  Concatenar cadenas de caracteres:

    ```
    let s1 = "Hola".to_string();
    let s2 = "mundo".to_string();
    let s3 = s1 + " " + &s2;  // La variable s1 se debe convertir en una referencia &str para poder concatenarla
    ```
3.  Acceder a los caracteres de una cadena:

    ```
    let s = "Hola mundo".to_string();
    let primer_caracter = s.chars().next().unwrap();  // Obtener el primer carácter de la cadena
    let tercer_caracter = s.chars().nth(2).unwrap();  // Obtener el tercer carácter de la cadena
    ```
4.  Dividir una cadena de caracteres:

    ```
    let s = "Hola,mundo".to_string();
    let partes: Vec<&str> = s.split(',').collect();  // Dividir la cadena en dos partes utilizando el carácter ","
    ```
5.  Buscar una subcadena dentro de una cadena:

    ```
    let s = "Hola mundo".to_string();
    let esta_mundo = s.contains("mundo");  // Verificar si la cadena contiene la subcadena "mundo"
    let posicion = s.find("mundo").unwrap();  // Encontrar la posición de la subcadena "mundo" en la cadena
    ```

Estos son solo algunos ejemplos de cómo trabajar con `String` en Rust. La documentación oficial de Rust proporciona más información y ejemplos detallados sobre cómo utilizar esta estructura.
