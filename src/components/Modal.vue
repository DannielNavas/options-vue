<template>
  <div>
    <button @click="toggle">
      Modal
    </button>
    <teleport to="body">
      <div v-show="show" class="modal">
        <h1>Titulo</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni recusandae fugit nihil</p>
        <button @click="toggle">
          Cerrar
        </button>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data() {
    return {
      show: false,
    };
  },
  methods: {
    toggle() {
      this.show = !this.show;
    },
  },
};
</script>
