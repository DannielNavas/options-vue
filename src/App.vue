<template>
  <div>{{ text }}</div>
  <Home first-name="Miles" last-name="Morales" otro="algo" />
</template>

<script>
import { provide } from 'vue';
import Home from './components/Home.vue';

export default {
  name: 'App',
  components: {
    Home,
  },
  data() {
    return {
      text: 'Hello World',
    };
  },
  setup() {
    provide('userName', 'spiderman');
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
