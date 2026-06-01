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
