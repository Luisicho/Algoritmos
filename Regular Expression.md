# Expresiones regulares
Las expresiones regulares son sentencias de caracteres que buscan un patron de busqueda, funcionan principalmente para filtrar cadenas invalidas, tambien para validadr estas mismas
## Elementos basicos de Expresiones Regulares
Para expresar una cantidad o segmento valido de una cadena, es importante poder construir la expresion regular, para esto se utilizan caracteres que expresan algo en especificos:
### El acentro circunflejo `^`
`^` Indica el inicio de la cadena o linea puede utilizarce para identificar todas las cadenas que contengan letras `^[a-z]` o utilizarlo dentro de `[]` para indicar `[^\w ]` las cadenas qeu NO se encuentren dentro de un grupo
### El signo de dolar `$`
`$` Indica el final de la cadena o linea por ejemplo se pueden encontrar todas las cadenas que finalizan con . `\.$`

### El punto `.`
`.` Se interpreta como cualquier caracter
```js
  let exp = /g.o/; // Puede ser gro, ggo,goo,glo,...
```
### La barra inversa o contrabarra `\`
`\` Se utiliza para _escapar_ un caracter siempre va acompañada de un caracter, por ejemplo si utilizo un `.` dentro de mi expresion, puede interpretarse como cualquier caracter pero con la barra inversa se colocaria un punto `\.`
```js
  let exp = /\./; // Puede ser .
```
Tambien esta barra puede dar significado especial a caracteres como son:
|  Combinacion |   Significado     |
| :--- | :---: |
|  `\t`   |   Representa una tabulador    | 

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

