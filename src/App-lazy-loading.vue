<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <!-- <component :is="componente"></component> -->
</template>

<script>
// TODO: importar componente sincrono
// import HelloWorld from './components/HelloWorld.vue';
// TODO: importar componente asincrono (lazy loading)
import { defineAsyncComponent } from 'vue';

const HelloWorld = defineAsyncComponent(() => import('./components/HelloWorld.vue'));

export default {
  name: 'App',
  components: {
    HelloWorld, // nombre del componente a utilizar
  },
  data() {
    return {
      componente: 'HelloWorld', // nombre del componente a utilizar en la directiva v-on:is="componente" o :is="componente"
    };
  },
};
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
