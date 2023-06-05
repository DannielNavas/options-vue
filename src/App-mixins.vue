<template>
  <div>{{ text }}</div>
  <div>{{ base }}</div>
</template>

<script>
import base from '@/mixins/base';

export default {
  name: 'App',
  mixins: [base],
  components: {
  },
  data() {
    return {
      text: 'Hello World',
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

<!-- los mixins tienen desventajas por que no se sabe que existe dentro de ellos  -->

<!-- al ser compartidos se necesita modificar y afecta a todos los componentes que lo usan -->

<!-- despues de la v3 el composition API es mejor que el uso de mixis -->
