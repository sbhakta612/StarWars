<template>
  <button @click="selectClickHandler">{{ movieObject.title }}</button>
</template>

<script>
export default {
  props: {
    movieObject: {
      type: Object,
      required: true
    }
  },
  emits: ['movieSelect'],
  methods: {
    selectClickHandler() {
      this.$emit('movieSelect', this.movieObject)
    }
  }
}
</script>

<style scoped>
button {
  background-color: black;
  height: 60px;
  width: 170px;
  font-family: 'Pathway Gothic One', sans-serif;
  color: #feda4a;
  border: 1px solid black;
}
button:hover {
  background-color: black;
  opacity: 60%;
  cursor: pointer;
}
</style>
