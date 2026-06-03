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
Push: Añade un nuevo objeto al final de Array
```js
  let nuevaFruta = frutas.push("naranja"); 

  console.log(frutas); // Imprime ["melon","sandia","fresa","naranja"]
```
Pop: Elimina el ultimo objeto del Array
```js
  let frutaEliminada = frutas.pop(); // Elimina a "naranja"

  console.log(frutas); // Imprime ["melon","sandia","fresa"]
```
Unshift: Añade un nuevo objeto al principio del Array
```js
  let nuevaFruta = frutas.unshift("piña"); 

  console.log(frutas); // Imprime ["piña,"melon","sandia","fresa"]
```
Shift: Elimina el primer objeto del Array
```js
  let frutaEliminada = frutas.shift("piña"); // Eliminó "piña"

  console.log(frutas); // Imprime ["melon","sandia","fresa"]
```
Splice: Elimina de un Arreglo los objetos para crear un nuevo Arreglo con los objetos eliminados, se especifica la posición y la cantidad de objetos a eliminar
```js
  let frutaEliminada = frutas.splice(1,2); // Eliminó "sandia","fresa" del arreglo

  console.log(FrutaEliminada); // Imprime ["sandia","fresa"]
  console.log(frutas); // Imprime ["melon"]
```
Slice: Crea una copia identica de un Array
```js
  let copyArray = frutas.slice; // Se copio Frutas

  console.log(copyArray); // Imprime ["melon"]
  console.log(frutas); // Imprime ["melon"]
```

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

## HashMaps
Esta estructura escencialmente es como la de un Array donde tenemos a un objeto y ademas un indice (index) que representa la posición del objeto dentro del Arreglo, con un HashMap contamos con un objeto o Value y un indice o Key, comunmente llamados Key-Value Pairs
|  Value | =>  | 12 | 10 | 37  | 54  |
| :--- | :---: | ---: | :--- | :---: | ---: |
|   Key  |  => | "gato" | "perro"  | "loro"  | "mono"  | 
