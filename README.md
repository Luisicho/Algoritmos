# Wiki de Algoritmos
## Lo Básico
### Algoritmo
La palabra algoritmo es una evolución del latín medieval _algorismus_ así se le conocía a **AI-Khwarizmi** un matemático que escribió reglas fundamentales de la aritmética. Hoy en día se asocia al cálculo y la resolución de problemas lógicos, en la informática es un conjunto de instrucciones definidas, ordenadas y acotadas para resolver un problema, realizar un cálculo o desarrollar una tarea.

### Partes de un Algoritmo
Las **tres partes** de un algoritmo son:
1. **Input (Entrada):** Esta es la información que entregamos al algoritmo, que más tarde se trabaja para ofrecer la solución esperada
2. **Proceso:** Es el conjunto de pasos para que, a partir de los datos de entrada, se llegue a una solución.
3. **Output (salida):** Son los resultados, a partir de la transformación de los valores de entrada durante el proceso.

De esta manera un algoritmo parte de un estado inicial, sigue una serie de pasos sucesivos y llega a un estado final que obtiene la solución.

### Características de los Algoritmos
Los algoritmos presentan una serie de características comunes:
* **Precisos:** Objetivos, sin ambiguedad.
* **Ordenados:** Presentan una secuencia clara y precisa para poder llegar a la solución.
* **Finitos:** Contienen un número determinado de pasos.
* **Concretos:** Ofrecen una solución determinada para la situación o problema planteados.
* **Definidos:** El mismo algoritmo debe dar el mismo resultado al recibir la misma entrada.

### Tipos de Algoritmos
Existen diversos algoritmos en funcion de distintos criterios. Pueden dividirse por **cuantitativos y cualitativos** tambien por **computacionales y no computacionales** incluso se pueden identificar por su **funcion** (qué hace) y su **estrategia** (como lo hace) aquí solamente describiré 5 tipos de algoritmos los cuales son:
1. **Algoritmo de búsqueda:** Estos localizan uno o varios elementos que presenten una serie de propiedades dentro de una estructura de datos.
2. **Algoritmos de ordenamiento:** Reorganizan los elementos de un listado según una relación de orden. Destacan el ordnamiento por inserción, por mezcla, por selección, de burbuja u el ordamiento rapido.
3. **Programación dinámica:** Método que reduce el tiempo de ejecución de un algoritmo, al dividir problemas en subproblemas y almacenar su solución, para que no haya que volver a calcularlos.
4. **Algoritmos voraces:** Adoptan la decisión más óptima en cada paso local con el objetivo de llgar a la mejor solución global.
5. **Algoritmos probabilísticos:** Utiliza un cierto grado de azar para proporcionar un resultado. De media proporcionan una buena solución al problema.

#### Algoritmos de búsqueda
Los algoritmos de búsqueda localizan uno o varios elementos que presenten una serie de propiedades dentro de una estructura de datos.
Las busquedas que sobresalen son:
* **Búsqueda secuencial:** En la que se compara el elemento a localizar con cada elemento del conjunto hasta encontrarlo o hasta que hayammos comparado todos.
* **Búsqueda binaria:** En conjunto de elementos ordenados, hace una comparación con el elemento ubicado en el medio y, si no son iguales, continúaa la búsqueda en la mitad donde puede estar. Y así sucesivamente en intervalos cada vez más pequeños de elementos.

##### Búsqueda binaria
La búsqueda binaria es una forma muy eficiente de encontrar los datos de un array, la principal desventaja es que _nuestro array debe estar ordenado_ 
La complejidad del algoritmo es de $$\log_{2}(n)$$ + 1 esto describe la cantidad de comparaciones maximas que se haran por busqueda dentro del algoritmo, en un ejemplo donde el array es de 9 objetos se realizaran 4 busquedas maximas para encontrar al elementro buscado.

```ts
function busquedaBinaria(arr: number[], objetivo: number): number {
    let izquierda = 0;
    let derecha = arr.length - 1;

    while (izquierda <= derecha) {
        // Calcular punto medio (evitando desbordamiento)
        let medio = Math.floor(izquierda + (derecha - izquierda) / 2);

        if (arr[medio] === objetivo) {
            return medio; // Elemento encontrado, retorna índice
        }

        if (arr[medio] < objetivo) {
            izquierda = medio + 1; // Buscar en la mitad derecha
        } else {
            derecha = medio - 1; // Buscar en la mitad izquierda
        }
    }

    return -1; // Elemento no encontrado
}
```
#### Algoritmos de ordenamiento
Esros algoritmos reorganizan los elementos de un listado según su relación de orden. La forma más habitual de ordenar son por medio de criterios numericos u orden lexicográfico. Si se ordena de forma eficiente se facilita la busqueda y los resultados legibles para usuarios asi como maquinas.
algunos algoritmos de ordenamiento son:
* **Ordenamiento de burbuja:** Compara cada elemento de la lista a ordenar con el siguiente e intercambia su posición si no está en el orden adecuado. Se revisa varias veces toda la lista hasta que no se necesiten más intercambios
Codigo ejemplo
```ts
function bubbleSort(arr: number[]): number[] {
  const n = arr.length;
  // Bucle externo para recorrer todo el arreglo
  for (let i = 0; i < n; i++) {
    // Bucle interno para comparar elementos adyacentes
    // -i porque los últimos 'i' elementos ya están ordenados
    for (let j = 0; j < n - 1 - i; j++) {
      if (arr[j] > arr[j + 1]) {
        // Intercambio de elementos
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return arr;
}
```
* **Ordenamiento por selección:** Vamos colocando el elemento más pequeño disponible en cada una de las posiciones de la lista de fomra consecutiva.
```ts
function selectionSort(arr: number[]): number[] {
    const n = arr.length;

    for (let i = 0; i < n - 1; i++) {
        // Buscar el mínimo en la parte no ordenada
        let minIndex = i;
        for (let j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }

        // Intercambiar el mínimo encontrado con el primer elemento
        if (minIndex !== i) {
            [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
        }
    }
    return arr;
}
```

* **Ordenamiento rápido(Quick sort):** Elegimos un elemento del conjunto (pivote) y reubicamos el resto a cada uno de sus lados, en función de si son mayores o menores que el elemento que estamos tomando como referencia. Repetimos el procedimiento en cada subconjunto.
```ts
function quickSort(arr: number[], left: number = 0, right: number = arr.length - 1): number[] {
  if (left < right) {
    const pivotIndex = partition(arr, left, right);
    
    // Recursively sort elements before and after partition
    quickSort(arr, left, pivotIndex - 1);
    quickSort(arr, pivotIndex + 1, right);
  }
  return arr;
}

/**
 * Helper function to partition the array
 */
function partition(arr: number[], left: number, right: number): number {
  // Choosing the last element as the pivot
  const pivot = arr[right];
  let i = left - 1;

  for (let j = left; j < right; j++) {
    if (arr[j] <= pivot) {
      i++;
      // Swap elements
      [arr[i], arr[j]] = [arr[j], arr[i]];
    }
  }

  // Swap the pivot element to its correct position
  [arr[i + 1], arr[right]] = [arr[right], arr[i + 1]];
  return i + 1;
}
```

* **Ordenamiento mezcla (Mergue sort):** La forma en como este metodo ordena un arreglo es dividiendo el problema en problemas pequeños, una ves creados los problemas pequeños comparamos cada uno de estos elementos y verificamos la condicion deseada, utilizando recursividad y una funcion que apoya el mezclar y el dividir los objetos del array.

```ts
function mergeSort<T>(arr: T[]): T[] {
  // Base case: arrays with 0 or 1 element are already sorted
  if (arr.length <= 1) {
    return arr;
  }

  // Divide: find the middle and split the array into two halves
  const middle = Math.floor(arr.length / 2);
  const left = arr.slice(0, middle);
  const right = arr.slice(middle);

  // Conquer: recursively sort both halves and merge them
  return merge(mergeSort(left), mergeSort(right));
}

/**
 * Helper function to merge two sorted arrays
 */
function merge<T>(left: T[], right: T[]): T[] {
  const result: T[] = [];
  let leftIndex = 0;
  let rightIndex = 0;

  // Compare elements and add the smaller one to the result
  while (leftIndex < left.length && rightIndex < right.length) {
    if (left[leftIndex] < right[rightIndex]) {
      result.push(left[leftIndex]);
      leftIndex++;
    } else {
      result.push(right[rightIndex]);
      rightIndex++;
    }
  }

  // Concatenate any remaining elements
  return result
    .concat(left.slice(leftIndex))
    .concat(right.slice(rightIndex));
}
```
