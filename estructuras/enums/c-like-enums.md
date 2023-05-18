# C-Like Enums

Los `C-like enums` (enumeraciones similares a las de C) son una forma de definir un tipo que puede tomar un conjunto de valores discretos. Estas enumeraciones son similares a las enumeraciones en C, pero con algunas diferencias importantes en su comportamiento.

Para definir un `C-like enum` en Rust, se utiliza la palabra clave `enum`, seguida de un identificador y una lista de variantes separadas por comas. Cada variante puede tener un valor asociado, que puede ser de cualquier tipo. Por ejemplo, la siguiente es una definición de una enumeración de días de la semana, con cada variante que tiene asociado un valor `u32`:

```
enum Weekday {
    Monday = 1,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday,
    Sunday,
}
```

En esta definición, la primera variante (`Monday`) se establece explícitamente en `1`, y las siguientes variantes (`Tuesday`, `Wednesday`, etc.) toman valores sucesivos en orden. Se puede utilizar esta enumeración de la siguiente manera:

```
let today = Weekday::Monday;
let day_number = today as u32;
```

En este ejemplo, `today` se establece en la variante `Monday` de la enumeración `Weekday`, y luego se convierte en un valor `u32` utilizando la sintaxis `as`. El valor resultante (`1`) se almacena en la variable `day_number`.

Es importante tener en cuenta que las enumeraciones en Rust son tipos fuertemente tipados y pueden incluir métodos y campos, lo que las hace mucho más flexibles y poderosas que las enumeraciones en C. Además, las variantes de una enumeración en Rust no necesitan tener un valor asociado y pueden ser simplemente identificadores. Por lo tanto, Rust permite la definición de enumeraciones mucho más ricas y complejas que las enumeraciones en C.
