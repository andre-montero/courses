## Teleports

En Vue 2 se llamaban portals y no eran una parte oficial de Vue, a partir de Vue 3 se denominan teleports. Los teleports son componentes especiales que nos da Vue para reflejar un componente en diferentes partes del documento. Su utilidad resalta cuando tenemos c&oacute;digo que logicamente pertenece a un componente, pero visualmente debe desplegarse en otro lado del documento (fuera de la vue app). Un ejemplo sería un modal que debe ser accedido desde el body:

#### App.vue

```html
<template>
    <div>
        <Modal />
    </div>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
    name: 'App',
    components: {
        Modal,
    },
};
</script>
```

#### Modal.vue

```html
<template>
    <div>
        <button @click='toggle'>Modal</button>
        <teleport to="body">
            <div v-show="show" class="modal">
                <h1>T&iacute;tulo</h1>
                <p>Lorem ipsum dolor</p>
                <button @click='toggle'>Cerrar</button>
            </div>
        </teleport>
    </div>
</template>

<script>
export default {
    data(){
        return {
            show: false;
        }
    },
    methods: {
        toggle(){
            this.show = !this.show
        },
    }
};
</script>
```