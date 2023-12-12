<template>
  <div id="app">
   <BuscadorSocio :socios="listaSocios"/>
   <WatcherPrueba />
   <OraculoWatcher />
  </div>
</template>

<script>
import BuscadorSocio from './components/BuscadorSocio.vue';
import OraculoWatcher from './components/OraculoWatcher.vue';
import WatcherPrueba from './components/WatcherPrueba.vue';


export default {
  name: 'App',
  components: {
    BuscadorSocio,
    WatcherPrueba,
    OraculoWatcher
},
  data() {
    return {
      listaSocios: [
        {
          numero:1234,
          nombre:'Juan Perez'
        },
        {
          numero:4321,
          nombre:'Maria Gomez'
        },
        {
          numero:6767,
          nombre:'Cristian Martinez'
        },
        {
          numero:8888,
          nombre:'Luis Ochoa'
        },
      ],
    };
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
