## Transiciones

En algunos casos, queremos aplicar una breve transici&oacute;n al mostrar u ocultar componentes. Para esto Vue nos brinda el componente `<transition></transition>`.

A continuaci&oacute;n se presenta un ejemplo de un menu, el cual aparece y desaparece al "clickar" un botón:

#### Menu.vue

```html
<template>
    <ul>
        <li>Option 1</li>
        <li>Option 2</li>
        <li>Option 3</li>
    </ul>
</template>
```

#### App.vue

```html
<template>
    <button @click="show = !show">Menu</button>
    <!-- <Menu v-if="show"/> -->
    <Menu v-show="show"/>
</template>

<script>
import Menu from './components/Menu.vue';

export default {
    name: 'App',
    components: { Menu },
    data(){
        return {
            show: false,
        };
    },
};
</script>
```

Para agregar transiciones en el ejemplo anterior colocamos el componente `<transition></transition>`. A este componente debemos darle un nombre para posteriormente referenciarlo en los est&iacute;los. 

Aunque no sea nuestro caso, transition puede contener e intercambiar 2 elementos, para ello en los est&iacute;los podemos referenciar elementos de entrada y salida: `.fade-enter` y `.fade-leave`. Adicional a esto, podemos agregar modificadores para referirnos al inicio, durante y fin de la transici&oacute;n: `.fade-enter-from`, `.fade-leave-active`, `.fade-enter-to`.

#### App.vue

```html
<template>
    <button @click="show = !show">Menu</button>
    <transition name="fade">
        <Menu v-show="show"/>
    </transition>
</template>

<script>
import Menu from './components/Menu.vue';

export default {
    name: 'App',
    components: { Menu },
    data(){
        return {
            show: false,
        };
    },
};
</script>

<style>
    .fade-enter-from,
    .fade-leave-to {
        opacity: 0;
    }

    .fade-enter-active, 
    .fade-leave-acive {
        transition: opacity 0.5s ease;
    }
</style>
```
