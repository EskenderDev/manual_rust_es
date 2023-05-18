# Operador de patrones $() y \*

El operador de patrones `$()` y `*` se utilizan en los macros de Rust para definir patrones de repetición.

El operador `$()` indica que se debe sustituir por cero o más elementos separados por coma. Por ejemplo, si se define el macro de la siguiente manera:

```
macro_rules! print_all {
    ($($x:expr),*) => {
        $(
            println!("{}", $x);
        )*
    };
}
```

Este macro toma cero o más expresiones separadas por coma como argumentos y las imprime en la consola. Si se llama al macro con la siguiente sintaxis:

```
print_all!(1, 2, 3);
```

Se expandirá a:

```
println!("{}", 1);
println!("{}", 2);
println!("{}", 3);
```

El operador `*` indica que el patrón anterior puede aparecer cero o más veces. Por ejemplo, si se define el siguiente macro:

```
macro_rules! foo {
    ($x:ident $($y:ident)*) => {
        println!("{}", stringify!($x));
        foo!($($y)*);
    };
    () => {}
}
```

Este macro toma un identificador como primer argumento, seguido de cero o más identificadores. Luego, imprime el nombre del primer identificador en la consola y llama recursivamente al macro con los identificadores restantes.

Si se llama al macro con la siguiente sintaxis:

```
foo!(a b c);
```

Se expandirá a:

```
println!("a");
println!("b");
println!("c");
```

Aquí, el operador `*` indica que el patrón `($y:ident)*` puede aparecer cero o más veces, lo que permite que el macro maneje cualquier cantidad de identificadores después del primer argumento.
