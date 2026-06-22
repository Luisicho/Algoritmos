# Expresiones regulares
Las expresiones regulares son sentencias de caracteres que buscan un patron de busqueda, funcionan principalmente para filtrar cadenas invalidas, tambien para validadr estas mismas
## Elementos basicos de Expresiones Regulares
Para expresar una cantidad o segmento valido de una cadena, es importante poder construir la expresion regular, para esto se utilizan caracteres que expresan algo en especificos:
* Aserciones: Indica el inicio o fin de cadena, asi como limites.
  * `^` Indica el inicio de la cadena o linea
  * `$` Indica el final de la cadena o linea

### Declaración
Las expresiones regulares se declaran de 2 formas:
La declaración literal de la expresión regular, es un patron que se encierra entre barras `/`. Estas expresiones regulares se compilan junto al script, si la expresion es constante ayuda en el rendimiento de ejecución.
```js
  let exp = /ab+c/;
```
Llamado a función `RegExp`. Esta forma de declarar una expresion regular se ejecuta en tiempo de ejecución, se recomienda declarar de esta forma si sabemos que la expresion regularar cambiara a menudo.
```js
  let exp = new RegExp("ab+c");
```

