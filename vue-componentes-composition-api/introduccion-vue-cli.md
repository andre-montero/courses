## Entorno de desarrollo

1. Extensi&oacute;n de Vue.js para el navegador.
1. Editor de c&oacute;digo o IDE configurado.
1. Vue CLI. `npm install -g @vue/cli`

## Creando el proyecto

1. Verifica la correcta instalaci&oacute;n de Vue CLI, para ello abre una terminal y digita el comando `vue`.
1. Crea un nuevo projecto usando el comando `vue create options`.
1. Para fines de aprendizaje selecciona "manually select features" aunque es posible elegir un preset.
1. Selecciona las features que necesites. A continuación se describe brevemente cada feature de la lista:  
    > • (x) Babel #Permite usar sintaxis de la versi&oacute;n m&aacute;s reciente de EcmaScript.  
    > • ( ) TypeScript #Habilita el lenguaje TypeScript.  
    > • ( ) Progressive Web App (PWA) Support #Permite crear aplicaciones WEB progresivas.  
    > • ( ) Router #Permite manejar rutas en una SPA.  
    > • ( ) Vuex #habilita el manejo del estado.  
    > • ( ) CSS Pre-processors #Permite configurar pre-procesadores CSS, como SASS.  
    > • (x) Linter / Formatter #Permite configurar un linter o formatter, como Prettier.  
    > • ( ) Unit Testing #habilita unit testing.  
    > • ( ) E2E Testing #habilita test end to end.  
1. Elige la versi&oacute;n de Vue.js, en este caso la 3.0.
1. Dependiendo de las features que seleccionamos seleccionar las configuraciones que nos solicita Vue CLI.
1. Esperar a que se cree el proyecto.

## Desarrollo del proyecto

Ya con el proyecto creado podremos ejecutar otros comandos como: 
- `npm run serve` - levanta un servidor de desarrollo.
- `npm run build` - genera el c&oacute;digo para producci&oacute;n.
- `vue ui` - permite acceder a las multiples funciones Vue CLI usando una interfaz gr&aacute;fica.

El comando `vue ui` levanta un servidor donde se aloja la interfaz gr&aacute;fica. Este comando no solo permite ejecutar comandos Vue CLI sino tambien el editar, crear y configurar proyectos.
