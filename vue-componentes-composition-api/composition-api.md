## Composition API

Hasta el momento dentro de los componentes Vue escribimos el apartado script en formato JSON (Options API). Vue 3 trajo una nueva sintaxis estilo programaci&oacute;n funcional (Composition API). Esta nueva sintaxis se volvi&oacute; la recomendaci&oacute;n oficial de Vue.

En la composition API se mantienen la mayor parte de conceptos que encontrabamos en la options API, lo &uacute;nico que cambia es la forma de implementaci&oacute;n.

Podemos notar la importancia de esta sintaxis al implementar componentes muy extensos, por ejemplo:

#### UserRepositories.vue

Al usar la options API se nos fuerza a mantener una estructura fija del c&oacute;digo, esto hace que no se adapte al orden que requiera nuestra app. Adem&aacute;s el tener componentes muy extensos dificulta al programador el desarollo al tener que consultar secciones que esten muy arriba.

```html
<template>
  <div>{{ user }} Repositories</div>
</template>

<script>
export default {
  props: {
    user: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      repositories: [],
      filters: {},
      searchQuery: "",
    };
  },
  computed: {
    filteredRepositories() {
      return null;
    },
    repositoriesMatchingSearchQuery() {
      return null;
    },
  },
};
</script>
```

#### App.vue

```html
<template>
  <UserRepositories :user="'Andre'"></UserRepositories>
</template>

<script>
import UserRepositories from "@/components/UserRepositories";

export default {
  name: "App",
  components: {
    UserRepositories,
  },
};
</script>
```

Para casos como el anterior Vue introdujo la Composition API. El hook setup() sirve como un punto de entrada a la Composition API, expone en su interior las configuraciones que le pasemos, previniendo las desventajas de la options API.

#### UserRepositories.vue + setup()

```html
<template>
  <div>{{ user }} Repositories</div>
</template>

<script>
export default {
  props: {
    user: {
      type: String,
      required: true,
    },
  },
  setup(props, context){
    return {
      repositories,
    }
  },
  data() {
    return {
      repositories: [],
      filters: {},
      searchQuery: "",
    };
  },
  computed: {
    filteredRepositories() {
      return null;
    },
    repositoriesMatchingSearchQuery() {
      return null;
    },
  },
};
</script>
```
