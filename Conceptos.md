# Conceptos que estudiar de programación JS
## Diferencia entre `==` y `===`
El operador `===` es uno llamado "Comparación estricta" esta comparacion se realiza entre 2 objetos, uno a la izquierda y otro a la derecha, la cualidad principal de esta comparación es que el compilador no se encarga de igualar los tipos de los objetos, toma de base el objeto y lo compará al otro

```js
  const comparacion1 = 1 === "1" ? false : true; //Arroja False
  const comparacion2 = 1 === 1 ? false : true; //Arroja True
```

El operador `==` es uno llamado "Comparación debil" esta comparación se realiza entre 2 objetos a su izquierda y derecha, la caracteristica principal será que en los operandos ocurre la Coerción de Tipos o en otras palabras la transformacion de los tipos de datos de los operandos a unos que sean comunes entre si y que puedan llevar a cabo la operación

```js
  const comparacion1 = 1 === "1" ? false : true; //Arroja True
  const comparacion2 = 1 === 1 ? false : true; //Arroja True
```

 ## Operador condicional (ternario)
