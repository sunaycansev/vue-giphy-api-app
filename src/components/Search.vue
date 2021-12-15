<template>
  <div class="search">
    <input
      type="text"
      v-model="query"
      placeholder="Search"
      @keydown.enter="handleSearch"
    />
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
      this.$emit("search-requested", this.query);
      this.query = "";
    },
  },
};
</script>

<style scoped>
.search {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 3rem;
}
.search input {
  padding: 10px 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 400px;
  margin-bottom: 3rem;
}
.search button {
  padding: 5px 15px;
  border: 1px solid #ccc;
  background-color: aquamarine;
  outline: none;
  font-size: 1rem;
  border-radius: 5px;
}
</style>
