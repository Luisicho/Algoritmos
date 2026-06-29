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
---------------------
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
---------------------
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
---------------------
## Operador de suma y resta
Estos son operadores unarios, que solamente funcionan con un solo operando, existen con prefijo y sin el, afectan directamente a la variable en cuestion.

```js
// Operador incremente y preincremento
let numero = 0;

console.log(numero++) // Imprime 0 despues internamente suma 1 a numero
// numero vale 1
console.log(++numero) // Primero internamente sumo 1 a numero, Imprime 2 
```
```js
// Operador decremento y predecremento
let numero = 2;

console.log(numero--) // Imprime 2 despues internamente resta 1 a numero
// numero vale 1
console.log(--numero) // Primero internamente resta 1 a numero, Imprime 0
```
---------------------
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
## Hoisting
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
---------------------
## Destructuring
Permite desempacar variables de un Array `[]` o propiedades de un objeto `{}` para asignarlos a variables
```js
  // Asignar a variables
  let a,b,rest;

  [a, b] = [10, 20];

  [a, b, rest] = [10, 20, 30, 40, 50];

  console.log(a); // Imprime 10
  console.log(b); // Imprime 20
  console.log(rest); // Imprime [30,40,50]

  let arra = [20,30,40,50,60]

  let [c, d, e] = arra;

  console.log(c); // Imprime 20 
  console.log(d); // Imprime 30 
  console.log(e); // Imprime 40 
  
  // Intercambiar elementos

  let arr = [0,1,2,3,4];

  [arr[0], arr[4]] = [arr[4], arr[0]]; // intercambia 0 y 4 de posición

  console.log(arr); // Imprime [4,1,2,3,0]
```

Se puede utilizar en funciones para facilitar el uso, asi como tener valores por defecto
```js

  function mostrarPersona({nombre, apellido, edad, trabajo="ninguno"}){
    console.log(`nombre: ${nombre} apellido: ${apellido} edad: ${edad} trabajo: ${trabajo}`)
  }

  persona1 = {
    nombre: "luis",
    apellido: "hernandez",
    edad: 26,
    trabajo: "programador",
  }

  persona2 = {
    nombre: "miguel",
    apellido: "macias",
    edad: 26,
  }

  mostrarPersona(persona1);
  // Imprime nombre: luis apellido: hernandez edad: 26 trabajo: programador
  mostrarPersona(persona2);
  // Imprime nombre: miguel apellido: macias edad: 26 trabajo: ninguno

```
---------------------
## Coerción
El compilador de _Javascrip_ cuando realiza comparaciones o combinas datos por defecto busca igualar los tipos de variables, esto se evalua dependiendo del operador utilizado, veamos varios ejemplos
### Suma o concatenacion "+"
```js
  let a = 1;
  let b = "2";

  // Operador "+" suma o concatencación
  if (a + b == "12"){ // Aqui la coerción cambia a 1 por string y concatena
    console.log(3); // es verdadera la condicion imprime 3
  }

  let c = 1 + "2";

  // Suma o concatenación
  console.log(c) // Imprime "12" la coerción transformo 1 a "1" y concateno a "2"

```
### Operadores "-, * , /"
Estos operadores tienden a realizar una coerción a favor de un resultado como numero.
```js
  let a = 1;
  let b = "2";

  // Operador "-" resta
  if (a - b == 1){ // Aqui la coerción cambia a 2 por numero y resta
    console.log(true); // es verdadera la condicion imprime true
  }

  let c = 1 * "2";

  // Multiplicación
  console.log(c) // Imprime 2 la coerción transformo 2 a numero y multiplica

  let d = 4 / "2";

  // Divición
  console.log(d) // Imprime 2 la coerción transformo 2 a numero y divide

```

### Truthy o Falsy
Esta coerción ocurre en condiciones y valida si un dato es falso o verdadero, en contexto normal cualquier valor es verdadero a menos que se defina como falso o pertenesca a `false, 0, "", null, undefined, NaN`
```js
  // Truthy
  if ("Texto"){ // Aqui la coerción cambia a "Texto" por verdadero
    console.log(true); // es verdadera la condicion imprime true
  }
  // Falsy
  if (null){ // Aqui la coerción cambia a null por falso
    console.log(true); // es falsa la condicion nunca se imprime true
  }
  let a = null;
  let b = "Texto";

  if(a && b){ // Se evalua a como falso y la condicion nunca entra
    console.log("Hola") // Nunca imprime "Hola"
  }

```

---------------------
# Sentencias
## For...In
Esta sentencia de bucle itera sobre las propiedades enumerables de un objeto, este bucle se utiliza comunmente para recorrer objetos.
```js
const objeto = {a: 1, b:2, c:3};

for (const propiedad in objeto){
  console.log(`${propiedad}: ${objeto[propiedad]}`);
}
// Imprime
// `a: 1`
// `b: 2`
// `c: 3`
```
## For...Of
Este es un bucle de sentencia, que itera sobre un objeto iterable, como un Array, String, Map, etc.

```js
let arr = [1,2,3];

for (const numero of arr) {
  console.log(numero); // Imprime 1,2,3
}
// Agregando un index
for (const [index, numero] of arr.entries()) {
  console.log(index + ` numero ` + numero); // Imprime 0 numero 1,1 numero 2,2 numero 3
}
```

