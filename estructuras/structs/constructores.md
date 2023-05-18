# Constructores

En Rust, no existe un concepto de "constructor" como en algunos otros lenguajes de programación, ya que la creación de nuevas instancias de estructuras y tipos de datos se realiza mediante una simple llamada a la función `new` o mediante la inicialización de los campos de la estructura.

En general, en Rust se puede crear una nueva instancia de una estructura o tipo de datos simplemente mediante la creación de una variable con el nombre del tipo, seguido de un par de llaves que contienen los valores iniciales para los campos de la estructura o tipo de datos.

Por ejemplo, supongamos que tenemos la siguiente estructura:

```
struct Persona {
    nombre: String,
    edad: u32,
}
```

Para crear una nueva instancia de `Persona`, podemos simplemente hacer lo siguiente:

```
let persona1 = Persona {
    nombre: String::from("Juan"),
    edad: 25,
};
```

En este caso, estamos creando una nueva instancia de `Persona` llamada `persona1` y especificando los valores iniciales para los campos `nombre` y `edad`. Para inicializar el campo `nombre`, estamos utilizando la función `from` del tipo `String` para crear una nueva cadena de texto a partir de un literal de cadena.

Si queremos proporcionar una función para crear nuevas instancias de una estructura, en lugar de simplemente inicializarla manualmente, podemos crear una función que devuelva una nueva instancia de la estructura con los valores iniciales proporcionados. Por convención, se suele nombrar a esta función `new`.

Por ejemplo, podemos definir la siguiente función `new` para la estructura `Persona`:

```
impl Persona {
    fn new(nombre: String, edad: u32) -> Persona {
        Persona { nombre, edad }
    }
}
```

En este caso, estamos definiendo un método `new` para la estructura `Persona`. Esta función toma dos parámetros, `nombre` y `edad`, y devuelve una nueva instancia de `Persona` con los valores iniciales proporcionados. En la definición del método `new`, estamos utilizando una sintaxis de inicialización de campos abreviada para crear la nueva instancia de la estructura, lo que significa que no es necesario especificar los nombres de los campos si los nombres de los parámetros de la función coinciden con los nombres de los campos de la estructura.

Podemos utilizar esta función `new` para crear nuevas instancias de `Persona` de la siguiente manera:

```
let persona2 = Persona::new(String::from("Pedro"), 30);
```

En este caso, estamos llamando al método `new` de la estructura `Persona` y proporcionando los valores iniciales para los campos `nombre` y `edad`. La función `new` devuelve una nueva instancia de `Persona` con estos valores.
