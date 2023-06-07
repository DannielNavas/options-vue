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
  setup(props, context) {
    // attrs emit expose slots
    console.log(context);

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

    // eslint-disable-next-line no-unused-vars
    const foo = () => {
      console.log('foo');
    };

    // TODO: hace publico las variables o un objeto
    context.expose({
      counter,
      obj,
      firstName,
      lastName,
      fullName,
    });

    return {
      counter,
      obj,
      // eslint-disable-next-line vue/no-dupe-keys
      firstName,
      // eslint-disable-next-line vue/no-dupe-keys
      lastName,
      fullName,
    };
  },
};
</script>
