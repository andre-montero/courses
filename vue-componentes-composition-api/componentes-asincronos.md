## Componentes as&iacute;ncronos

En las aplicaciones Vue.js todos los componentes cargan desde el inicio. Cuando un proyecto crece esta carga empieza a ser pesada. Notemos que hay componentes Vue que no requerimos que carguen desde el inicio, sino que carguen unicamente cuando sean solicitados. Para estos casos usamos componentes as&iacute;ncronos, como se muestra a continuaci&oacute;n:

```html
<template>
    <HelloWorld />
</template>

<script>
//import { HelloWorld } from './components/HelloWorld.vue';
import { defineAsyncComponent } from 'vue;';

const HelloWorld = defineAsyncComponent(() => import('./components/HelloWorld.vue'));

export default {
    name: 'App',
    components: {
        HelloWorld,
    }
}
</script>
```
