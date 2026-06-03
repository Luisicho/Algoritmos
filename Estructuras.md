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
  let FrutaEliminada = frutas.pop(); // Elimina a "naranja"

  console.log(frutas); // Imprime ["melon","sandia","fresa"]
```
Unshift: Añade un nuevo objeto al principio del Array
```js
  let nuevaFruta = frutas.unshift("piña"); 

  console.log(frutas); // Imprime ["piña,"melon","sandia","fresa"]
```
Shift: Elimina el primer objeto del Array
```js
  let FrutaEliminada = frutas.shift("piña"); // Eliminó "piña"

  console.log(frutas); // Imprime ["melon","sandia","fresa"]
```
Splice: Elimina de un Arreglo los objetos para crear un nuevo Arreglo con los objetos eliminados, se especifica la posición y la cantidad de objetos a eliminar
```js
  let FrutaEliminada = frutas.splice(1,2); // Eliminó "sandia","fresa" del arreglo

  console.log(FrutaEliminada); // Imprime ["sandia","fresa"]
  console.log(frutas); // Imprime ["melon"]
```
Slice: Crea una copia identica de un Array
```js
  let copyArray = frutas.slice; // Se copio Frutas

  console.log(copyArray); // Imprime ["melon"]
  console.log(frutas); // Imprime ["melon"]
```
