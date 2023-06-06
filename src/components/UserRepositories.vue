<template>
  <h1>{{ user }} repositories</h1>
</template>

<script>

export default {
  name: 'UserRepositories',
  props: {
    user: {
      type: String,
      required: true,
    },
  },
  setup(props, ctx) {
    console.log(props);
    console.log(ctx);
    return {
      repositories: [],
      filters: {},
      searchQuery: '',
    };
  },
  data() {
    // return {
    //   repositories: [],
    //   filters: {},
    //   searchQuery: '',
    // };
  },
  computed: {
    filteredRepositories() {
      return null;
    },

  },
};
</script>
