## ¿Cómo llega un script al navegador?

El código que hemos escrito, en el proyecto, "vive" entre 2 etiquetas script. Esta no es la unica forma de implementarlos, tambien podemos traer scripts externos, sin embargo existen muchas formas de traerlos, las cuales veremos en esta clase.

## DOM

Cuando llega un HTML al navegador, este lo empieza a parsear: va leyendo
etiqueta por etiqueta y va creando el DOM usando una estructura de árbol.

```html
<html>
  <head>
    <title>text</title>
  </head>
  <body>
    <h1>text</h1>
    <p>text<code>text</code>text</p>
  </body>
</html>

<!-- prettier-ignore -->
html
|
|-- head
|   |
|   |-- title
|   |   |
|   |   |-- #text
|
|-- body
|   |
|   |-- h1
|   |   |
|   |   |-- #text
|   |
|   |-- p
|   |   |
|   |   |-- #text
|   |   |-- code
|   |   |   |
|   |   |   |-- #text
|   |   |
|   |   |-- #text
```

Cuando este proceso termina por completo, es cuando obtenemos el evento `DOMContentLoaded`. Con esto tenemos la certeza de que el documento se cargó y esta disponible para manipular. Sin embargo, aún cabe la posibilidad de que recursos externos como imagenes y hojas de estilo aún no hayan cargado, para eso esperamos al evento `load`. En este último evento, no sólo se cargo el html, sino todos los recursos externos.

Como dato adicional tambien contamos con 2 eventos adicionales después de `load`:

- `beforeunload`: indica que el usuario se va de la página, pero aún podemos comprobar cosas, como si guardo sus cambios y preguntarle si realmente quiere irse.
- `unload`: cuando el usuario casi se fue, pero aún podemos hacer operaciones como enviar estadísticas.

## Scripts externos o embebidos

Todo script tiene un llamado y una ejecución. Cuando el DOM se esta parseando si encuentra una etiqueta `<script>` detiene este proceso, es decir ningun elemento HTML, debajo del script, se lee hasta que termine de procesarse. Por tanto, es importante el lugar donde colocamos los scripts, de hecho el mejor lugar es colocarlos al final de nuestro body.

La diferencia entre los scripts embebidos y externos, es que estos ultimos cuentan con el atributo `src` y el paso de la petición (fetching), lo que añade un retardo. Para evitar este retardo existen atributos como `async` y `defer` que veremos en la siguiente sección.

## Atributos async y defer

Estos atributos se aplican unicamente en scripts externos. El atributo `async` permite que el paso de petición (fetching) no detenga la aplicación. Mientras que el atributo `defer` indica que el fetching se realiza en donde colocamos la etiqueta script, pero el paso de ejecución se hace hasta el final del parseado. Para mayor claridad, el siguiente gráfico muestra el tiempo de parseado del HTML y los pasos del script, los pasos entre barras indican una pausa en el parseado.

```
Embebido:       ---------|execution|------
Externo:        ---|fetch|execution|------
Externo(async): ----fetch|execution|------
Externo(defer): ----fetch------|execution|
```
