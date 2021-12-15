<template>
  <div class="search">
    <input type="text" v-model="query" />
    <button @click="handleSearch">Search</button>
  </div>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      query: "",
    };
  },
  methods: {
    handleSearch() {
      console.log(this.query);
    },
  },
};
</script>

<style scoped></style>
