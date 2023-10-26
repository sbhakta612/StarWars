<template>
  <div v-if="movieObject == undefined"></div>
  <div v-else>
    <h1>Episode {{ movieObject.episode_id }}</h1>
    <h2>{{ movieObject.title }}</h2>
    <p>{{ movieObject.opening_crawl }}</p>
  </div>
</template>

<script>
export default {
  props: {
    movieObject: {
      type: Object,
      required: false
    }
  }
}
</script>

<style scoped>
h1,
h2,
p {
  text-align: center;
  background-color: black;
  max-width: 500px;
}
</style>
