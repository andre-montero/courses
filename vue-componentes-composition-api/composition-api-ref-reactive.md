## ref

Para declarar variables reactivas en la Composition API se usa el hook ref.
A continuaci&oacute;n podemos ver un ejemplo de este:

```html
<template>
  <div>{{ text }}</div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const text = ref("Hola Vue");

    console.log("setup", text.value);

    return {
      text,
    };
  },
  mounted() {
    console.log("mounted", this.text);
  },
};
</script>
```

Como podemos notar, el valor de las variables reactivas dentro de setup se lee como una propiedad de la variable `.value`. Sin embargo, al exponer las variables reactivas, mediante el return de setup, al componente completo podemos observar que Vue nos permite acceder al valor directamente.

## reactive

Cuando requerimos trabajar con valores de objetos reactivos debemos usar el hook reactive:

```html
<template>
  <div>{{ obj.counter }}</div>
</template>

<script>
import { reactive } from "vue";

export default {
  setup() {
    const obj = reactive({ counter:0 });

    setInterval(() => obj.counter++, 500);

    return {
      obj,
    };
  },
};
</script>
```
