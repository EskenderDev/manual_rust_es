# Patrones

La estructura `match` se utiliza para comparar un valor con una serie de patrones y ejecutar el código correspondiente al patrón que coincida con el valor. Los patrones que se pueden utilizar en una estructura `match` en Rust son los siguientes:

* Literales: un valor concreto, como un número o un caracter.
* Variables: un nombre de variable que se asigna al valor que coincide con el patrón.
* Wildcard: un guión bajo (`_`), que coincide con cualquier valor.
* Structs: un patrón que se ajusta a un valor de una estructura, donde se proporcionan los valores de los campos que se compararán.
* Enums: un patrón que se ajusta a un valor de una enumeración, donde se especifica el nombre del campo de la enumeración que se está comparando y se proporcionan los patrones que coinciden con los valores posibles del campo.
* Tuplas: un patrón que se ajusta a una tupla, donde se proporcionan los patrones que coinciden con los valores de los elementos de la tupla.
* Slices: un patrón que se ajusta a un slice, que es una referencia a una sección de una matriz, donde se proporcionan los patrones que coinciden con los elementos del slice.
* Punteros: un patrón que se ajusta a un puntero, donde se proporciona un patrón que coincide con el valor apuntado por el puntero.
* Rangos: un patrón que se ajusta a un rango de valores, como un rango numérico o un rango de caracteres.

En una estructura `match`, los patrones se especifican como ramas del árbol `match`, y el código correspondiente a cada patrón se escribe en un bloque de código separado. Cada rama del árbol `match` puede incluir uno o más patrones, y si se proporciona un comodín `_`, se puede incluir como un patrón de captura de cualquier valor que no haya sido capturado por otros patrones.

Es importante recordar que cada rama del árbol `match` debe ser exhaustiva, lo que significa que debe incluir un patrón que capture todos los valores posibles del valor que se está comparando en la estructura `match`. Si se omite una rama, el compilador de Rust mostrará un error.
