# Conceptos que estudiar de programación JS
## Diferencia entre `==` y `===`
El operador `===` es uno llamado "Comparación estricta" esta comparacion se realiza entre 2 objetos, uno a la izquierda y otro a la derecha, la cualidad principal de esta comparación es que el compilador no se encarga de igualar los tipos de los objetos, toma de base el objeto y lo compará al otro

```js
  const comparacion1 = 1 === "1" ? false : true; //Arroja False
  const comparacion2 = 1 === 1 ? false : true; //Arroja True
```

El operador `==` es uno llamado "Comparación debil" esta comparación se realiza entre 2 objetos a su izquierda y derecha, la caracteristica principal será que en los operandos ocurre la Coerción de Tipos o en otras palabras la transformacion de los tipos de datos de los operandos a unos que sean comunes entre si y que puedan llevar a cabo la operación

```js
  const comparacion1 = 1 == "1" ? false : true; //Arroja True
  const comparacion2 = 1 == 1 ? false : true; //Arroja True
```

 ## Operador condicional (ternario) y sentencia ifelse
El _operador condicional ternario_ es un unico operador que usa 3 operandos. Ejecuta la condición del primer operando y dependiendo a este resultado ejecuta una accion u otra. Igualmente a como se utiliza un _ifelse_ statement, el operador ternario compara valores y retorna un resultado, es en el uso pleno de la palabra una "expresion"

```js
  condition ? val1 : val2
```

La sentencia _ifelse_ es un bloque de control o estructura de control, permite la comparacion de una condición y ejecuta el codigo en base a esta condición, controlando el codigo en esta estructura, de tal forma que en comparación a el _operador condicional ternadio_ no retorna un valor, sino que maneja el codigo entro de su estructura.

```js
  if (condition){
    val1
  } else {
    val2
  }
```

## Operador de propagación
Existe un operador que separa los elemento de un array `...` este operador es una forma sencilla de hacer `split` a un arreglo, el trabajo de `...` es **Propagacion o Desempaquetado** basicamente elimina todo corchete de un arreglo o separa elementos de un string para crear un objeto desempaquetado.

```js
let arr = ["mano", "pie"];
let arr2 = ["cabeza", ...arr, "zapato"];

console.log(arr2) // Imprime ["cabeza", "mano", "pie", "zapato"]
```
Se puede utilizar incluso par copiar array silimar a split
```js
let arr = [[1],[2],[3]];
let copyarr = [...arr]; // Como usar arr.split("")

console.log(copuarr); //Imprime [[1],[2],[3]]
```
Remplaza el suo de apply en funciones, divide los elemento para encajar en una función
```js
function myfuncion(x,y,z){}
let arr = [1,2,3]
myfuncion(...arr) // Como usar myfuncion.apply(null, arr);
```
Tambien puede usarse muchas veces dentro de una funcion ademas de separa un array y dejar un resultado util para la funcion
```js
function myfuncion(x,y,z,a,b,c){}
let arr = [1,2,3]
myfuncion(0, ...arr,4, ...[5]) // los parametros serian myfuncion(0,1,2,3,4,5)
```


## Var, Let y Const
Estas palabras reservadas se utilizan para declarar variables dentro del codigo JavaScript, su uso esta muy relacionado a su _Alcance_ (Scope)

```js
  var obj1;
  let obj2;
  const obj3;
```
### Var
Esta palabra reservada cuenta con un alcance de función, en palabras sencillas cuando es declarada este valor se podra utilizar en cualquier parte del codigo mientras se encuentre dentro de la función donde se declaro `var`

```js
  funtion () {
    var a = "hola";
    console.log(a); // Imprime "hola" en consola
  }
    console.log(a); // Error no se declaro la variable a

// Ejemplo como variable global o declaración de variable en el contexto

  var a = "hola";
  funtion () {
    console.log(a); // Imprime "hola" en consola
  }

  console.log(a); // Imprime "hola" en consola
```

De esta manera la palabra reservada `var` crea variables que perduran en una función, cuenta con caracteristicas muy especiales como lo es el __hoisting__ 
#### Hoisting
Este es un comportamiento del los contextos de ejecución de JavaScript donde las declaraciones de variables y funciones son movidas a la parte superior del codigo para ser ejecutadas primero (de forma coloquial). Tecnicamente las variables y funciones son asignadas a la memoria durante la fase de compilación, esto genera que se puedan utilizar en cualquier parte del codigo y declarar en cualquier parte del codigo o contexto, ya que al ser cargadas con anterioridad en memoria su uso no se limita dentro del codigo.

```js
  funtion () {
    console.log(a); // Imprime Indefinido en consola, pero a ya existe dentro del codigo como indefinido
    var a = "hola";
    console.log(a); // Imprime "hola" en consola, ya que se acaba de asignar valor a la variable a
  }
  console.log(a); // Error no se declaro la variable a

// Ejemplo como variable global o declaración de variable en el contexto

  funtion () {
    console.log(a); // Imprime Indefinido en consola, pero a ya existe dentro del codigo como Indefinido
    a = "adios" 
    console.log(a); // Imprime "adios" en consola, ya que se acaba de asignar valor a la variable a
  }
  var a = "hola"; // como si se escribe a = "hola"
  console.log(a); // Imprime "hola" en consola, ya que se acaba de asignar valor a la variable a
```
La declaración de una variable con la palabra reservada `var` solamente ocurre una vez, el uso repetido de la declaración de una variable con el mismo nombre solamente se someterá a una asignacion nueva

```js
  var a = "hola"; // Se declara a como igual a "hola"
  var a = "adios"; // Se asigna a la variable a el valor de "adios"
  var a = "no"; // es similara a escribir en codigo a = "no"
```

### Let
Esta palabra reservada cuenta con un alcance de función y de bloque, esto quiere decir que la variable solamente existirá dentro de una funcion o un bloque de funcion.
```js
  funtion () {
    let a = "hola";
    console.log(a); // Imprime "hola" en consola
  }
    console.log(a); // Error no se declaro la variable a

// Ejemplo como variable bloque

  funtion () {
    if(b == true){
      let a = "Adios"
      console.log(a); // Imprime "Adios" en consola
    }
      console.log(a); // Error no se declaro la variable a
  }
```

### Const
Esta palabra reservada cuenta con un alcance de función y de bloque, esto quiere decir que la variable solamente existirá dentro de una funcion o un bloque de funcion. la particularidad de esta palabra es que asigna un valor constante a una variable, no se pueden redeclarar, ni modificar en condiciones normales.
```js
  funtion () {
    const a = "hola";
    console.log(a); // Imprime "hola" en consola
  }
    console.log(a); // Error no se declaro la variable a

// Ejemplo como variable bloque

  funtion () {
    if(b == true){
      const a = "Adios"
      console.log(a); // Imprime "Adios" en consola
    }
      console.log(a); // Error no se declaro la variable a
  }
```
