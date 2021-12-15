<template>
  <div>
    <ul>
      <li v-for="gif in gifs" :key="gif.name">
        <img :src="gif.images.fixed_height.url" :alt="gif.name" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Preview",
  props: {
    gifs: {
      type: Array,
    },
  },
};
</script>
<style scoped>
li {
  list-style: none;
  float: left;
  margin: 20px;
}
</style>
