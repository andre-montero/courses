## Registro de componentes

Para usar componentes en una app de vue que usa Single File Components (SFC), es decir, archivos .vue debemos importar estos componentes usando JavaScript:

```html
<template>
    <HelloWorld></HelloWorld>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
    components: {
        HelloWorld,
    }
}
</script>
```

tambien es posible renombrar los componentes registrados de la siguiente manera:

```html
<template>
    <Hello></Hello>
</template>

<script>
    import HelloWorld from "./components/HelloWorld.vue";

    export default {
        components: {
            Hello: HelloWorld,
        }
    }
</script>
```

## Secci&oacute;n style

Dentro de los archivos .vue la secci&oacute;n **style** permite agregar estilos a nuestra app.

Una caracter&iacute;stica de estos estilos es que se aplican de manera global, es decir, para todo el proyecto. Si queremos que los estilos solo apliquen para el componente en el que nos encontramos debemos usar el atributo **scoped**:

```html
<style scoped>
    h3{
        margin: 40px 0 0;
    }
</style>
```

## Componentes din&aacute;micos

Cuando requerimos cambiar entre componentes, por ejemplo en una interfaz de pesta&#241;as, usamos componentes din&aacute;micos. Vue, proporciona un componente genérico `<component></component>`, el cual admite el prop `is` como vemos a continuaci&oacute;n:

```html
<template>
    <component :is="componente">
    </component>
</template>
<script>
    import HelloWorld from "./components/HelloWorld.vue";

    export default {
        components: {
            Hello: HelloWorld,
        }
        data(){
            return {
                componente: "Hello"
            }
        }
    }
</script>
```