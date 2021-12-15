<template>
  <div id="app">
    <h3 v-if="isLoading">Loading...</h3>
    <search @search-requested="handleSearch"></search>
    <preview :gifs="gifs"></preview>
  </div>
</template>

<script>
import Search from "@/components/Search";
import Preview from "@/components/Preview";
export default {
  name: "App",
  data() {
    return {
      gifs: [],
      isLoading: true,
    };
  },
  methods: {
    doQuery(url) {
      fetch(url)
        .then((res) => res.json())
        .then((res) => {
          this.gifs = res.data;
          this.isLoading = false;
        });
    },
    handleSearch(query) {
      this.isLoading = true;
      this.gifs = [];
      const url = `https://api.giphy.com/v1/gifs/search?api_key=soYWlUH3Hkczx8fQjVaVHDpHjlUjGlCj&q=${query}&limit=25&offset=0&rating=g&lang=en`;
      this.doQuery(url);
    },
  },
  components: { Preview, Search },
  created() {
    const url =
      "https://api.giphy.com/v1/gifs/trending?api_key=soYWlUH3Hkczx8fQjVaVHDpHjlUjGlCj&limit=25&rating=g";
    this.doQuery(url);
  },
};
</script>

<style></style>
