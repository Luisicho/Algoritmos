# Tipos de Algoritmos
## Binary Search (busqueda binaria)
Este es un algoritmo de busqueda, que se utiliza para encontra la posición de un valor especifico en una lista u arreglo ordenado, sus caracteristicas principales son:
Binary Search:
- Se utiliza para encontrar eficientemente un elemento dentro de una lista u arreglo ordenado
- Eficiente: O(log2(n))

## Depth-First Search (DFS)
Se utiliza en grafos y arboles, la idea de este algoritmo de busqueda es ir a lo mas profundo del arbol, y al llegar si no se encontro la solución regresar un nodo para volver a recorrer nuevamente a profundidad, esta accion de regresar al nodo padre se le conoce como _Backtracking_, es importante que se tenga en cuenta lo siguiente para llevar a cabo el DFS:
* Se debe tener un arreglo llamado Visitados[] el cual llevara el registro de todos los nodos ya visitados

Sus caracteristicas són:
Depth-First Search (DFS):
- Inicia en el nodo Root y viaja hasta el fondo del arbol, para luego realizar _Backtracking_
- Utiliza un array de nodos ya visitados
- Eficiencia: O(V + E), V = Vertices/Nodos, E = Edges/Ramas

## Breadth-First Search (BFS)
Se utiliza en arboles, este algoritmo de busqueda necesita de un array de nodos visitados, y uno de vecinos al nodo, el algoritmo recorre en primer lugar los nodos vecinos al nodo raiz, y mientras los recorre agrega nuevas entradas al array de vecinos para más tarde recorrerlos. Basicamente el algoritmo decorre los nodos que se agregan al array vecinos y va colocando los ya visitados en el array de visitados.
Sus caracteristicas son:
Breadth-First Search (BFS):
- Revisa cada nodo un nivel abajo antes de brincar al proximo nivel
- Utiliza un arreglo visitados[] para llevar una lista de los ya visitados
- Muy utilizado en los algoritmos de ajedres que predice movimientos
- Runtime: O(V + E), V = Vertices/Nodos, E = Edges/Ramas

