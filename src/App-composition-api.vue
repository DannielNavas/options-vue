<template>
  <div>{{ text }}</div>
  <UserRepositories :user="'DannielNavas'" />
</template>

<script>
import UserRepositories from './components/UserRepositories.vue';

export default {
  name: 'App',
  components: {
    UserRepositories,
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
