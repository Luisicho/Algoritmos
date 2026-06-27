# Estructuras de datos
## Array
Es una colección de información ordenada, su estructura contiene diversos objetos aqui una tabla con sus caracteristicas principales
- Read: O(1)
- Insertion: O(n)
- Deletion: O(n)
- Rapida en lectura pero lenta en inserción y eliminación
El array coloca un identificador (index) a sus objetos para poder mandarlos llamar, esto facilita su lectura.
```js
  let frutas = ["melon","sandia","fresa"]

  console.log(frutas[0]); // Imprime "melon"
```
Array cuenta con funciones utilez a la hora de manejar su colección estas son:
### Push
Añade un nuevo objeto al final de Array y devuleve el nuevo tamaño del arreglo.
```js
  let nuevaFruta = frutas.push("naranja"); 

  console.log(frutas); // Imprime ["melon","sandia","fresa","naranja"]
```
### Pop
Elimina el ultimo objeto del Array y devuele el elemento eliminado.
```js
  let frutaEliminada = frutas.pop(); // Elimina a "naranja"

  console.log(frutas); // Imprime ["melon","sandia","fresa"]
```
### Unshift
Añade un nuevo objeto al principio del Array
```js
  let nuevaFruta = frutas.unshift("piña"); 

  console.log(frutas); // Imprime ["piña,"melon","sandia","fresa"]
```
### Shift
Elimina el primer objeto del Array
```js
  let frutaEliminada = frutas.shift("piña"); // Eliminó "piña"

  console.log(frutas); // Imprime ["melon","sandia","fresa"]
```
### Splice
Elimina de un Arreglo los objetos para crear un nuevo Arreglo con los objetos eliminados, se especifica la posición y la cantidad de objetos a eliminar
```js
  let frutaEliminada = frutas.splice(1,2); // Eliminó "sandia","fresa" del arreglo

  console.log(FrutaEliminada); // Imprime ["sandia","fresa"]
  console.log(frutas); // Imprime ["melon"]
```
### Slice
Crea una copia identica de un Array
```js
  let copyArray = frutas.slice; // Se copio Frutas

  console.log(copyArray); // Imprime ["melon"]
  console.log(frutas); // Imprime ["melon"]
```
### Sort
Ordena el array por defecto con su unicode convirtiendo todo a string, pero puede colocarse una condición que maneje el orden
```js
  let nums = [1, 3, 2, 0]
  // Si la condición es mayor a 0 significa que la variable a es mayor que b
  // Si la condición es menor a 0 significa que la variable b es mayor que a
  nums.sort((a,b) => a - b); // Ordena
  console.log(nums); // Imprime [0, 1, 2, 3]
```
### Map
Crea un HashMap del arreglo, para poder ejecutar en cada elemento una funcion especifica
```js
  let nums = [1, 3, 2, 0]
  // Ejecuta en cada elemento del Array la suma de +1
  nums.map((n) => {return n + 1;});
  console.log(nums); // Imprime [2, 4, 3, 1]
```
### Find
Retorna el valor del primer elemento que se encuentre con una condicion o expresion regular, su funcion callback contiene 
* element: El elemento actual que se esta procesando
* index: El indice del elemento actual que se procesa
* array: El array desde el cual se esta llamando la función
```js
  let nums = [1, 3, 2, 0]
  let newNum = nums.find((element) => element > 2); // Busca el numero mayor a 2 y lo retorna

  console.log(newNum); // Imprime 3
```
### At
Retorna un elemento en la posicion que se especifica.
```js
  let nums = [1, 3, 2, 0]

  console.log(numero `${nums.at(1)}`); // Imprime 3
  console.log(numero `${nums.at(0)}`); // Imprime 1
  console.log(numero `${nums.at(-1)}`); // Imprime 0
  console.log(numero `${nums.at(-2)}`); // Imprime 2
```
### Join
Une todos los elementos de un array en una cadena, y devuelve esta cadena nueva unida.
```js
  let nombres = ["luis", "miguel", "hernandez"];

  let nuevoNombre = nombres.join(" ");

  console.log(nuevoNombre); // Imprime "luis miguel hernandez"
  
```
### Entries
Esta funcion retorna un nuevo *array iterator* con las llaver pares de cada objeto
```js
  let nombres = ["luis", "miguel", "hernandez"];

  let nuevoArreglo = nombres.estries();

  for (let elemento of nuevoArreglo){
    console.log(elemento); // Imprime los pares [0, "luis"]  [1, "miguel"]  [2, "hernandez"]
  }

  // Imprimir con ...
  console.log([...nuevoArreglo]); // imprime [[0, "luis"]  [1, "miguel"]  [2, "hernandez"]]

```
----------------------------------
## Linked Lists
Son similares a un Array ya que siguen guardando listas ordenadas de elementos, sin embargo cuentan con una diferencia grande cuando se habla de almacenar los elementos en memoria, una lista cuenta con algo que se llama apuntador (pointer) es basicamente el elemento que se esta seleccionando o haciendo énfasis dentro de la lista. 
Esto implica varias cosas:
* Primero el elemento que se encuentre en una lista puede o no tener espacio entre el proximo elemento, pero si cuenta con un apuntador a donde se encuentre el proximo elemento

|  12 |        |     |       |       |      | 54  |        |       |     | 95   |
| :--- | :---: | ---: | :--- | :---: | ---: | :--- | :---: | ---: | :--- | :---: | 
|     |       |  37 |        |       |      |     |        | 20    |     |      |

En esta situación 12 tiene un espacio grande de vacios hacia 54, para ello la lista coloca un apuntador directo de 12 a 54 para asi hacerlo el proximo objeto en la lista, esto facilita la insercion y la eliminacion, sus caracteristicas principales
- Read: O(n)
- Insertion: O(1)
- Deletion: O(1)
- Lento para lectura pero muy eficiente en inserción y eliminación.

Esta estrucutra cuenta con funciones interesantes, aqui colocaré unos ejemplos para uso practico de la estructura
### Insertar
Para insertar en una extructura así se necesita remplazar el elemento apuntado por el que buscamos insertar
```js
  let numeros = new ListNode();

  numeros = 1; // Se agrega 1 al primer nodo de la lista
  numeros.next; // Se mueve al proximo nodo de la lista, dejando a 1 atras

  console.log(numeros.val) // Imprime null que es el valor de un nodo nuevo
```
Para poder insertar en una nueva lista de nodos sin recorrer el nodo se utilizan los punteros, los cuales se moveran al proximo nodo sin que el apuntador principal se vea afectado

```js
  let numeros = new ListNode(); // Se crea nodo con su apuntador numeros
  let puntero = numeros; // Se crea nuevo apuntador que apunta al principio de la lista de nodos

  puntero = 1; // Se agrega 1 al primer nodo de la lista
  puntero.next; // Se mueve al proximo nodo de la lista, dejando a 1 atras

  console.log(numeros.val) // Imprime 1 que es el nodo al que se agrego
  console.log(puntero.val) // Imprime Null que es el nodo nuevo de la lista de nodos
```
### Eliminar
Un nodo dentro de una lista de nodos no se elimina como tal, solamente se apunta a un nodo distinto, esto lo elimina.
```js
  /* Mi lista de nodos base es [5,6,7] mi apuntador esta en 5*/
  let numeros = new ListNode(); // Se crea nodo con su apuntador numeros
  let puntero = numeros; // Se crea nuevo apuntador que apunta al principio de la lista de nodos

  /* Elimino 6 de los nodos*/
  puntero.next = puntero.next.next; // Elimino el apuntador de 5 -> 6

  console.log(numeros.val) // Imprime 5 que es el primer nodo
  console.log(numeros.next.val) // Imprime 7 que es el nodo que sigue de la lista de nodos
```
----------------------------------
## HashMaps
Esta estructura escencialmente es como la de un Array donde tenemos a un objeto y ademas un indice (index) que representa la posición del objeto dentro del Arreglo, con un HashMap contamos con un objeto o Value y un indice o Key, comunmente llamados Key-Value Pairs
|  Value | =>  | 12 | 10 | 37  | 54  |
| :--- | :---: | ---: | :--- | :---: | ---: |
|   Key  |  => | "gato" | "perro"  | "loro"  | "mono"  | 

Sus caracteristicas principales son:
HashMaps:
- Read: O(1)
- Insertion: O(1)
- Deletion: O(1)
- Similar a Arreglos pero con identificadores (index) con nombres; sin orden y de rapida busqueda

Existen funciones para HashMaps muy utilez, las explicare por aqui
### Filter
Esta funcion filtra los objetos de un HashMap segun las condiciones especificadas, cada objeto dentro del HashMap se somete a este filtro y si resulta ser verdadero es elegido para ser parte del nuevo HashMap.

```js
  let numeros = new Map([1,2,3,4,5,6]);

  // Se filtan los numeros (num) mayores a 4
  let filtroNumeros = numeros.filter(num => num > 4);

  console.log(filtroNumeros); // Imprime [5,6] los mayores a 4
```
### Reduce
Esta funcion reune o recopila todos los elementos de un HashMap en un solo elemento.

```js
  let numeros = new Map([1,2,3,4,5,6]);

  // En este caso suma los numeros hasta hacer uno solo
  // El primer parametro es la función que se repetira el segundo es el valor inicial del total
  let sumTotal = numeros.reduce((total, curNum)=>{return total + curNum},0);

  console.log(sumTotal); // Imprime 21 que es la suma del arreglo 1+2+3+4+5+6
```

### Set
Esta es la forma de insertar valores a un Map

```js
  const map1 = new Map();
  map1.set(`bar`, 1); // Agrega bar con key 1

  console.log(map1); // Imprime { 'bar' => 1 }
```

### Has
Esta es la forma de buscar si un elemento existe dentro de un HashMap, retorna true o false, si lo encuentra o no.

```js
  const map1 = new Map();
  map1.set(`bar`, 1); // Agrega bar con key 1

  console.log(map1.has(`bar`)); // Imprime true
  console.log(map1.has(`bat`)); // Imprime false
```
----------------------------------
## Staks (Pilas)
Es una estructura Last In-First Out (LIFO) esta estructura cuenta con funciones similares a la inserción y eliminación, estas son Push que añade elementos a la pila, Pop que elimina el ultimo elemento de la fila, Peak que revisa el ultimo elemento añadido de la pila, funciona asi como una pila de hotcakes, para comerla el ultimo de los hotcakes sera el primero en comerse. Sus caracteristicas principales son:
Stacks:
- Push: O(1)
- Pop: O(1)
- Peak: O(1)
----------------------------------
## Queue (Filas)
Esta estructura se concidera First In-First Out (FIFO), esta estructura cuenta con funciones Enqueue que añade un elemento al principio de la fila, Dequeue que elimina el primer archivo agregado a la fila y Front que revisa cual es el primer archivo agragado a la fila, si lo comparamos con una fila en un supermercado tiene una funcionalidad igual, los primeros clientes en llegar serán los primeros en ser atendidos, sus caracteristicas son:

Queues:
- Enqueue: O(1)
- Dequeue: O(1)
- Front: O(1)
----------------------------------
## Trees (Arboles)
Los arboles son estructuras de datos jerarquicos, donde existes Nodos (nodes) y ramas (edges), tambien existe un nodo raiz (Root), cuando los nodos son unidos por las ramas se forma una figura similara un arbol. Los nodos dependen de su nodo padre, esta es otra forma de referirse al nodo superiro a ellos, "el nodo padre tiene nodos hijos".
Sus caracteristicas principales son:

 Trees:
- Read/Search: O(log n)
- Insertion: O(log n)
- Deletion: O(log n)
- Nodos se conectan con ramas; Nodo raiz, conexiones padre-hijo

Uno de los arboles mas comunes son los Binary Tree (Arboles Binarios) estos arboles cuentan con una conexion no mayor a 2 ramas que a su vez se conectan a 1 solo nodo por rama, ademas los nodos de la deecha son mayores a su nodo padre y los izquierdos son menores a su nodo padre. Son muy utilizados en ejercicios de programación.

|   |   | 10 |  | |   |
| :--- | :---: | ---: | :--- | :---: | ---: |
|     | 5  |  | 5  |   |  | 
|  2   | 3  |   |  1 | 4  |  | 
|     |   |  |   | 4  |4  | 

Existen formulas ya utilizadas para poder realizar funciones basicas dentro de los arboles binarios, por ejemplo, recorrer un arbol buscando un dato, sumar los datos de un arbol, o intercambiar los nodos de un arbol.

### Buscar
```js
var existeTree = function(root, value){
  if(root === null){
    return false; 
  } else {
    inLeft = existeTree(root.left, value);
    inRight = existeTree(root.right, value);
    return root.data === data || inLeft || inRight;
  }
}
```
### Intercambiar
```js
var invertTree = function(root) {
    if(root == null){
        return null;
    } else {
        invertTree(root.left);
        invertTree(root.right);
        [root.left, root.right] = [root.right, root.left];
        /* IGUAL A
        let tmp = root.left;
        root.left = root.right;
        root.right = tmp; */
    }
    return root;
}
```
### Suma Total
```js
var sumaTree = function(root){
  if(root === null){
    return 0; 
  } else {
    leftSum = sumaTree(root.left);
    rightSum = sumaTree(root.right);
    return root.data + leftSum + rightSum;
  }
}
```
### Buscar Maximo
```js
var maxTree = function(root){
  if(root === null){
    return -Infinity; 
  } else {
    leftMax = maxTree(root.left);
    rightMax = maxTree(root.right);
    return Math.max(root.data, leftMax, rightMax);
  }
}
```
### Altura de Arbol
```js
var altTree = function(root){
  if(root === null){
    return 0; 
  } else {
    leftHeight = altTree(root.left);
    rightHeigh = altTree(root.right);
    return 1 + Math.max(leftMax, rightMax);
  }
}
```

----------------------------------
## Grafos
Esta estructura es no lineal y une a objetos para formar estructuras complejas, cuentan con nodos (node) y ramas (edges) solamente que a diferencia de un arbol estos se unen y pueden volverse a unir entre distintos nodos, tecnicamente una lista y un arbol son grafos con caracteristicas delimitadas. Sus ramas pueden ser direccionadas o no direccionadas, asi como tambien pueden ser recursivas que se apunten a si mismas.
Sus caracteristicas son:
Graphs:
- Traversal/Search: O(V + E) (V: numerio de vertices, E: numero de ramas)
- Insertion: O(1)
- Deletion: O(1)

----------------------------------
# Tipo de datos
## String
Es una cadena de caracteres inmutable, o sea no puede modificarse a menos que se utilice una funcion especifica de string
```js
  let cadena = "hola"

  console.log(cadena); // imprime "hola"
```
Puede declararse de varias formas pero es importante recordar que existe la forma primitiva utilizando los tipos de datos primitivos, y la creacion de un objeto String, en Javascript ambos son tomados como objetos String, pero eso lo facilita el compilador y no significa que sean iguales.
```js
  let cadena = "hola"
  let cadena2 = 'de nuevo hola'
  let cadena3 = `mas holas`

  const str = "hola" // forma primitiva de declarar

  const str2 = new String("hola"); // forma correcta de declarar
```
El objeto String cuenta con propiedades y funciones, la unica propiedad con la que cuenta es _length_ esta retorna el tamaño de la cadena y cuenta con 34 funciones para string.
```js
  let str = "hola";

  console.log(str.length); // Imprime 4
```

### Replace
Es utilizado cuando quieres remplazar un substring dentro de un string, tambien funciona colocando expresiones regulares y colocando el parametro que quieres remplazar luego del parametro que se remplazá. Esto ocurre solamente con un solo parametro el primero que se encuentre.
```js
  let cadena = "hala"

  let nuevaCad = cadena.replace("a", "_");

  console.log(nuevaCad); // imprime "h_la"
```

```js
  let cadena = "Mi nombre es luis"

  let nuevaCad = cadena.replace("luis", (match) {
    return match.toUpperCase();
  });

  console.log(cadena); // imprime "Mi nombre es LUIS"
```

### Match
Es una funcion que sirve para encontrar expresiones regulares dentro de una cadena, devuelve un array con las propiedades
* Que se buscó (Match)
* Index de donde esta
* La expresion completa
* Que grupo es la expresion regular

```js
  let cadena = "hola a todos soy luis miguel";

  let macheado = cadena.match("todos");

  console.log(macheado); // retorna objeto
  /*
  [
    "todos",
    7,
    "hola a todos soy luis miguel",
    undefined
  ]
  */

```

### Split
Es utilizado cuando quieres dividir un string en substrings, estos substring se retornan dentro de un array, y no modifica al string original.

```js
  let cadena = "hola a todos soy luis miguel";

  let macheado = cadena.split(" ");

  console.log(macheado); // Imprime ["hola", "a", "todos", "soy", "luis", "miguel"]

```
```js
  let cadena = "miguel";

  let macheado = cadena.split();

  console.log(macheado); // Imprime ["miguel"]

  let macheado2 = cadena.split("");

  console.log(macheado2); // Imprime ["m", "i", "g", "u", "e", "l"]

```

### Trim
Esta función elimina los espacios vacios antes y despues de un string
```js
  let cadena = "      miguel      ";

  let recordato = cadena.trim();

  console.log(recordato); // Imprime ["miguel"]

  let cadena2 = "     luis miguel      ";

  let recordato2 = cadena2.trim();

  console.log(recordato2); // Imprime ["luis miguel"]

```
### Search
Busca si una expresion regular se cumple dentro de una cadena, si no es asi retorna `-1`
```js
  let cadena = "miguel";

  console.log(cadena.search(`i`)); // Imprime 1
  console.log(cadena.search(`j`)); // Imprime -1

```
