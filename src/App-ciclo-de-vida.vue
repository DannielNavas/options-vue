<template>
  <div>{{ text }}</div>
  <button @click="update">cambiar</button>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      text: 'Hello World',
    };
  },
  beforeCreate() {
    console.log('beforeCreate', this.$data, this.$el);
  },
  created() {
    console.log('created', this.$data, this.$el);
  },
  mounted() {
    console.log('mounted', this.$data, this.$el);
  },
  beforeUpdate() {
    console.log('beforeUpdate', this.$data, this.$el);
  },
  updated() {
    console.log('updated', this.$data, this.$el);
  },
  beforeUnmount() {
    console.log('beforeUnmount', this.$data, this.$el);
  },
  unmounted() {
    console.log('unmounted', this.$data, this.$el);
  },
  methods: {
    update() {
      this.text = 'Hello World 2';
    },
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
