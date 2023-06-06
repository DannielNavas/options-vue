<template>
  <div>{{ counter }}</div>
  <div>Home {{ obj }}</div>
  <div>{{ firstName }} {{ lastName }}</div>
  <div>{{ fullName }}</div>
</template>

<script>
import {
  computed,
  onMounted, reactive, ref,
  toRefs,
  watch,
} from 'vue';

export default {
  props: {
    firstName: {
      type: String,
      required: true,
    },
    lastName: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    onMounted(() => {
      console.log('mounted');
    });
    const counter = ref(0);
    // TODO: solo para objetos simples
    const obj = reactive({ counter: 0 });

    setInterval(() => {
      obj.counter += 1;
      counter.value += 1;
    }, 1000);

    watch(() => obj.counter, (newValue, oldValue) => {
      console.log(newValue, oldValue);
    });

    // const firstName = ref('John');
    // const lastName = ref('Doe');

    const { firstName, lastName } = toRefs(props);

    const fullName = computed(() => `${firstName.value} ${lastName.value}`);

    return {
      counter,
      obj,
      firstName,
      lastName,
      fullName,
    };
  },
};
</script>
