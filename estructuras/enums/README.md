# Enums

Las enumeraciones (también conocidas como `enums`) son un tipo de datos que permiten definir un conjunto finito de valores posibles. Cada valor posible se llama "variante", y puede tener un nombre y un valor asociado. Las enumeraciones son útiles para representar tipos de datos que tienen un conjunto limitado de valores posibles, como los días de la semana, los estados de una máquina de estados finitos o las opciones de un menú.

Para definir una enumeración en Rust, se utiliza la palabra clave `enum`, seguida de un identificador y una lista de variantes separadas por comas. Cada variante puede tener un nombre y un valor asociado, y las variantes se separan por comas. Por ejemplo, la siguiente es una definición de una enumeración de días de la semana, con cada variante que tiene un valor asociado:

```
enum Weekday {
    Monday(u32),
    Tuesday(u32),
    Wednesday(u32),
    Thursday(u32),
    Friday(u32),
    Saturday(u32),
    Sunday(u32),
}
```

En esta definición, cada variante representa un día de la semana, y cada variante tiene un valor asociado que es un número entero sin signo de 32 bits. Los valores asociados se pueden utilizar para almacenar información adicional relacionada con cada variante.

Para crear una instancia de una enumeración en Rust, se utiliza el nombre de la enumeración seguido del nombre de la variante y cualquier valor asociado que se desee. Por ejemplo, para crear una instancia de la variante `Monday` de la enumeración `Weekday`, se podría hacer lo siguiente:

```
let monday = Weekday::Monday(1);
```

En este ejemplo, se crea una instancia de la variante `Monday` con un valor asociado de `1`.

Las enumeraciones en Rust son tipos de datos fuertemente tipados, lo que significa que cada instancia de una enumeración tiene un tipo específico que está determinado por la variante que se utiliza. Además, las enumeraciones en Rust pueden tener métodos y campos, lo que las hace mucho más flexibles y poderosas que las enumeraciones en otros lenguajes de programación.
