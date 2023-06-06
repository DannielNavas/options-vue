<template>
  <div>{{ counter }}</div>
  <div>Home {{ obj }}</div>
</template>

<script>
import { onMounted, reactive, ref } from 'vue';

export default {
  setup() {
    onMounted(() => {
      console.log('mounted');
    });
    const counter = ref(0);
    const obj = reactive({ counter: 0 });

    setInterval(() => {
      obj.counter += 1;
      counter.value += 1;
    }, 1000);

    return {
      counter,
      obj,
    };
  },
};
</script>
