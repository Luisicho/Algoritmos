# Tipos de Algoritmos
## Algoritmos de Busqueda
### Binary Search (busqueda binaria)
Este es un algoritmo de busqueda, que se utiliza para encontra la posición de un valor especifico en una lista u arreglo ordenado, sus caracteristicas principales son:
Binary Search:
- Se utiliza para encontrar eficientemente un elemento dentro de una lista u arreglo ordenado
- Eficiente: O(log2(n))

### Depth-First Search (DFS)
Se utiliza en grafos y arboles, la idea de este algoritmo de busqueda es ir a lo mas profundo del arbol, y al llegar si no se encontro la solución regresar un nodo para volver a recorrer nuevamente a profundidad, esta accion de regresar al nodo padre se le conoce como _Backtracking_, es importante que se tenga en cuenta lo siguiente para llevar a cabo el DFS:
* Se debe tener un arreglo llamado Visitados[] el cual llevara el registro de todos los nodos ya visitados

Sus caracteristicas són:
Depth-First Search (DFS):
- Inicia en el nodo Root y viaja hasta el fondo del arbol, para luego realizar _Backtracking_
- Utiliza un array de nodos ya visitados
- Eficiencia: O(V + E), V = Vertices/Nodos, E = Edges/Ramas

### Breadth-First Search (BFS)
Se utiliza en arboles, este algoritmo de busqueda necesita de un array de nodos visitados, y uno de vecinos al nodo, el algoritmo recorre en primer lugar los nodos vecinos al nodo raiz, y mientras los recorre agrega nuevas entradas al array de vecinos para más tarde recorrerlos. Basicamente el algoritmo decorre los nodos que se agregan al array vecinos y va colocando los ya visitados en el array de visitados.
Sus caracteristicas son:
Breadth-First Search (BFS):
- Revisa cada nodo un nivel abajo antes de brincar al proximo nivel
- Utiliza un arreglo visitados[] para llevar una lista de los ya visitados
- Muy utilizado en los algoritmos de ajedres que predice movimientos
- Runtime: O(V + E), V = Vertices/Nodos, E = Edges/Ramas

## Algoritmos de Ordenamiento
### Insertion Sort
Este algoritmo ordena una lista por medio de comparaciones, compara el primer elemento y lo compara al segundo, si es mayor son intercambiados, luego se compara con el siguiente, sucede la misma condición, ademas de volver a comparar si este nuevo elemento menor es menor a los anteriores los volvera a intercambiar, dejando del lado derecho la lista desordenada y poco a poco del lado izquierdo la lista ordenada.
Sus caracteristicas son:
Insertion Sort:
- Examina cada elementode la lista, comparandolo con su previo elemento e intercambiandolo, entonces vuelve a comparar el elemento de la derecha hasta encontrar su posición correcta
- Simple algoritmo de ordenamiento para pequeñas bases de datos o ya ordenadas casi en su totalidad
- Runtime:
  - Mejor caso: O(n) cuando la lista ya eta ordenada
  - Peor caso: O(n^2) cuando la lista no tiene nada ordenado  

### Merge Sort
Este algoritmo ordena separando el arreglo en arreglos mas pequeños, separa un arreglo a la mitad hasta llegar a un arreglo con 2 elementos los cuales se comparan para ver cual es mayor, luego se intercambian si esto es verdad, despues vuelve a unir los arreglos separados y crea arreglos mas grandes que vuelven a compararse hasta llegar al arreglo principal que es mas facil de ordenar.
Sus caracteristicas son:
Merge Sort:
- Un "divide y venceras" este algoritmo rompe el problema en problemas más pequeños y los resuelve recursivamente
- Inicia diviendo un arreglo en subarreglos mas sencillos
- Mescla los subarreglos y los compara para colocarlos de una forma ordenada
- Continua mesclando los subarreglos hasta conseguir todo el arreglo ordenado
- Runtime: O(n log(n)) en ambos casos peor y mejor, haciendolo eficiente con bases de datos grandes

### Quick Sort
Este algoritmo ordena mediante un pivote, este debe ser la mitad del arreglo, se compara con los elementos del arreglo y los separa mayores y menores al pivote, despues vuelve a ocurrir esto dentro de los arreglos separados recursivamente, asta tener nuestro arreglo ordenado.
Sus caracteristicas son:
Quick Sort:
- Un algoritmo complejo que sigue el ejemplo de "divide y venceras" y es recursivo
- Selecciona un pivote, idealmente el centro del arreglo, y divide en dos subarrays uno mayor al pivote y otro menor al pivote
- Continua recursivamente este proceso con cada subarreglo hasta tener el arreglo ordenada.
- Utiliza el pivote y lo mueve al final del array, luego apunta al primero y penultimo elemento del array
- Compara los elementos y si uno es mayor los intercambia hasta que los dos apuntadores se juntan, aqui el primer pivote es intercambiado en la posición donde los dos apuntadores se intercambiaron
- Ya tenemos las sublistas con los numeros mayores y menores al pivote, ahora se realiza lo mismo en las sublistas mayores y menores al pivote
- Runtime:
  - Mejor caso: O(b log(n)), cuando el pivote divide consistentemente la lista en partes iguales
  - Peor caso: O(n^2), cuando el pivote seleccionado crea constantemente divisiones desbalanceadas
