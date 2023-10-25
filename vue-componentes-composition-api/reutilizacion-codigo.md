## Mixins

Entre los usos m&aacute;s importantes de Vue.js esta la reutilizaci&oacute;n de c&oacute;digo, una forma de hacer esto es usando mixins.

Los mixins, exclusivos de Vue options API, permiten escribir el JSON de los componente en archivos JS los cuales pueden ser llamados mediante imports dentro de los componentes de Vue. Se puede ver como una especie de herencia o composici&oacute;n de componentes.

Al importar un mixin y agregarlo a la lista `mixins: [mixinName]` en un componente, automaticamente tenemos acceso a las variables y m&eacute;todos dentro de este. Si alguna variable o m&eacute;todo tiene el mismo nombre en el componente y en el mixin, Vue dar&aacute; prioridad al componente.

Las desventajas m&aacute;s importante de los mixins recae en el no saber que partes del c&oacute;digo dentro de un componente proviene del mixin sin ver el c&oacute;digo interno de este. 

<div style="color: gold;">
<b>USO NO RECOMENDADO</b>

Los mixins continuan siendo soportados por mera compatibilidad. Se recomienda su reemplazo por las "Composable Functions" exclusivas de la Composition API
</div>

A continuaci&oacute;n podemos ver un ejemplo de uso de los mixins. Los mixins normalmente se encuentran en la carpeta src/mixins dentro del proyecto. Tal es el caso del siguiente archivo base.js:

#### base.js

```javascript
export default {
  data() {
    return {
      something: "texto algo",
    };
  },
  created() {
    console.log("base created");
  },
};

```

Una vez creado el mixin accedemos a este usando import y colocandolo en la lista del atributo mixins como podemos ver a continuaci&oacute;n:

#### App.vue

```html
<template>
  <div>{{ something }}</div>
</template>

<script>
import base from "@/mixins/base";

export default {
  name: "App",
  mixins: [base],
};
</script>
```

Notemos la sintaxis del import `@/mixins/base`, el @ se usa para referirse a la carpeta src.
