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
