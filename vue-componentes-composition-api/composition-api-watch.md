## Watch

El hook watch nos permite &ldquo;escuchar&rdquo; el momento en el que una avariable reactiva cambia su valor, tambien nos permite acceder a su antiguo y nuevo valor.

El siguiente ejemplo, aprovecha el c&oacute;digo que usamos cuando vimos reactive, el cual consiste en un contador que incrementa cada 500ms. Si nos fijamos importamos y usamos watch dentro de setup de la misma manera que otros hooks vistos anteriormente.

```html
<template>
  <div>{{ obj.counter }}</div>
</template>

<script>
  import { reactive, watch } from "vue";

  export default {
    setup() {
      const obj = reactive({ counter: 0 });

      setInterval(() => obj.counter++, 500);

      watch(
        () => obj.counter,
        (newValue, prevValue) => console.log(prevValue, newValue)
      );

      return {
        obj,
      };
    },
  };
</script>
```

La funci&oacute;n watch recibe 2 parametros:

1. el valor que quieres escuchar
1.
