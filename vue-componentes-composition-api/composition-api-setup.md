## Funci&oacute;n setup

Setup permite el uso de la options API como hemos venido trabajando, per tambien nos permite la sintaxis de la Composition API. A continuaci&oacute;n podemos observar un ejemplo de ambas API:

```html
<template>
    <div>Hola</div>
</template>

<script>
import { onMounted } from 'vue';

export default {
    setup(){
        onMounted(() => {
            console.log('Mounted');
        });
    },
    created(){

    },
    // mounted(){

    // }
}
</script>
```

Cabe agregar, que las funciones de ciclos de vida tienen el mismo nombre en ambas API, solo que la Composition API inicia con el sufijo on y con may&uacute;scula inicial. Por esto, mounted en la Options API es onMounted en la Composition API.
