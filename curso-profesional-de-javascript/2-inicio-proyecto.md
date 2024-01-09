## Inicio del proyecto

En este curso vamos a desarrollar una aplicación de video. En toda plataforma de video hay un componente especial en el desarrollo, el media player. Por eso desarrollaremos este feature de forma modular, es decir, vamos a desarrollar plugins que nuestro reproductor implementará, extendiéndo así sus funcionalidades.

## Primer paso

Crearemos nuestros primeros archivos usando `npm init -y`, donde `-y` es una bandera que le dicta a npm que le diga sí a todas las preguntas que haga. Esto nos creará un archivo **package.json** que lo sustituiremos por el siguiente:

```json
{
  "author": "usuario <correo>",
  "description": "proyecto del curso profesional de javascript de platzi.",
  "keywords": ["cursos", "platzi", "javascript", "profesional"],
  "license": "MIT",
  "main": "index.js",
  "name": "media-player",
  "version": "1.0.0"
}
```

Una vez tengamos esto listo procedemos a instalar el paquete live-server. Para ello ejecutamos el siguiente comando `npm i -D live-server`, donde `i` significa install y `-D` development, esto ultimo indica que el paquete no se usará en producción.

Una vez instalado agregamos al package.json lo siguiente:

```json
  "scripts": {
    "start": "live-server"
  },
```

Ahora podemos usar el comando `npm start` para llamar a live-server. Con esto podemos empezar a desarrollar nuestra aplicación.

## ¿Qué sigue?

1. Crear una carpeta assets.
2. Elegir un video de nuestro agrado y colocarlo dentro de assets.
3. Crear el index.css y colocarlo dentro de assets.
4. Crear nuestro index.html en la carpeta raiz.

#### index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Media Player</title>
    <link rel="stylesheet" href="./assets/index.css" />
  </head>
  <body>
    <header>
      <h1>Media Player</h1>
      <p>An extensible media player.</p>
    </header>
    <main>
      <video class="movie">
        <source src="./assets/video.extension" />
      </video>
      <br />
      <button>Play/Pause</button>
    </main>

    <script>
      const video = document.querySelector("video");
      const button = document.querySelector("button");

      button.onclick = () => video.play();
    </script>
  </body>
</html>
```

**Nota: Las diferentes modificaciones al proyecto se podran ver en el historial de git, en la carpeta media-player.**
