# Macros procedurales

Aquí hay algunos ejemplos de macros procedurales en Rust:

1. Macro para imprimir información de depuración

```rust
#[macro_export]
macro_rules! debug {
    () => {
        eprintln!("[DEBUG] at {}:{} in {}", file!(), line!(), module_path!());
    };
    ($msg:expr) => {
        eprintln!("[DEBUG] at {}:{} in {}: {}", file!(), line!(), module_path!(), $msg);
    };
}
```

Esta macro se puede usar para imprimir información de depuración con la ubicación de archivo, número de línea y módulo en el que se llama la macro.

2. Macro para crear estructuras

```rust
macro_rules! define_struct {
    ($name:ident { $($field:ident: $ty:ty),* }) => {
        struct $name {
            $( $field: $ty ),*
        }
    };
}
```

Esta macro se puede usar para definir una estructura de Rust con campos y tipos personalizados, como se muestra a continuación:

```rust
define_struct!(Person {
    name: String,
    age: u32,
    is_student: bool,
});
```

3. Macro para generar código de prueba

```rust
#[macro_export]
macro_rules! assert_approx_eq {
    ($a:expr, $b:expr) => {
        let eps = 1.0e-6;
        let diff = ($a - $b).abs();
        assert!(diff < eps, "{} is not approximately equal to {}", $a, $b);
    };
    ($a:expr, $b:expr, $eps:expr) => {
        let diff = ($a - $b).abs();
        assert!(diff < $eps, "{} is not approximately equal to {} within an epsilon of {}", $a, $b, $eps);
    };
}
```

\


Esta macro se puede usar para verificar si dos valores son aproximadamente iguales en un nivel de tolerancia dado. Puede ser útil en pruebas de números en coma flotante.
