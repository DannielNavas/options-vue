<template>
  <div>{{ counter }}</div>
  <div>Home {{ obj }}</div>
  <div>{{ firstName }} {{ lastName }}</div>
  <div>{{ fullName }}</div>
  <div>{{ userName }}</div>
  <button ref="btn">Click!</button>
</template>

<script setup>
import {
  computed,
  defineExpose,
  defineProps,
  inject,
  onMounted, reactive, ref,
  toRefs,
  watch,
} from 'vue';

const props = defineProps({
  firstName: {
    type: String,
    required: true,
  },
  lastName: {
    type: String,
    required: true,
  },
});

// attrs emit expose slots
// console.log(context);

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

// de esta forma no es reactivo
const userName = inject('userName');

// TODO: no existen los emementos dentro de setup no hay uso de this
// uso de convencion el null
const btn = ref(null);

// esto retorna un null por la creacion de
// referencia en el setu setup se ejecuta antesdel ciclo de vida de vue
console.log(btn.value); // null

// desde el watch se puede hacer el uso desde js para el manejo de los elementos en el dom
watch(btn, (valor) => {
  console.log(valor);
});

defineExpose({
  firstName,
  lastName,
  fullName,
  userName,
  btn,
});

</script>
