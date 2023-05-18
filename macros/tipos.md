# Tipos

Hay dos tipos principales de macros: las macros de declaraciones y las macros de expresiones.

Las macros de declaraciones se utilizan para generar definiciones de tipos, funciones y otros elementos de declaración. Estas macros se definen utilizando la palabra clave `macro_rules!` seguida de un patrón y un cuerpo que generan la declaración. Por ejemplo, una macro de declaración que genera una estructura de datos podría tener el siguiente aspecto:

```
macro_rules! my_struct {
    ($name:ident { $($field:ident : $ty:ty),* }) => {
        struct $name {
            $($field : $ty),*
        }
    };
}
```

Esta macro se puede invocar con una sintaxis similar a la siguiente:

```
my_struct!(MyStruct { foo: i32, bar: String });
```

Esto generará la siguiente estructura de datos:

```
struct MyStruct {
    foo: i32,
    bar: String,
}
```

Las macros de expresiones, por otro lado, se utilizan para generar código que se evalúa en tiempo de ejecución. Estas macros se definen utilizando la palabra clave `macro` seguida de un nombre de macro y un cuerpo que genera una expresión. Por ejemplo, una macro de expresión que genera una suma de dos números podría tener el siguiente aspecto:

```
macro add {
    ($x:expr, $y:expr) => {
        $x + $y
    };
}
```

Esta macro se puede invocar con una sintaxis similar a la siguiente:

```
let result = add!(2 + 2, 3 + 3);
```

Esto generará la siguiente expresión:

```
let result = 4 + 6;
```

En general, las macros de declaraciones se utilizan para generar código en tiempo de compilación, mientras que las macros de expresiones se utilizan para generar código en tiempo de ejecución.
