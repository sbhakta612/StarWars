<template>
  <div id="loading" v-if="movieObjects.length == 0"></div>
  <div v-else class="movie-list">
    <MovieCard
      v-for="movieObject in movieObjects"
      :movieObject="movieObject"
      @movieSelect="movieSelectHandler"
      :key="movieObject.episode_id"
    />
  </div>
</template>

<script>
import MovieCard from './MovieCard.vue'

export default {
  components: {
    MovieCard
  },
  data() {
    return {
      movieObjects: []
    }
  },
  emits: ['movieSelect'],
  async created() {
    const response = await fetch('https://swapi.dev/api/films')
    const result = await response.json()

    this.movieObjects = result.results
  },
  methods: {
    movieSelectHandler(movieObject) {
      this.$emit('movieSelect', movieObject)
    }
  }
}
</script>

<style scoped>
#loading:before {
  content: 'Loading...';
}
@keyframes l4 {
  to {
    clip-path: inset(0 -1ch 0 0);
  }
}

#loading {
  color: #feda4a;
  font-family: 'Pathway Gothic One', sans-serif;
  width: fit-content;
  font-weight: bold;
  font-family: monospace;
  font-size: 30px;
  clip-path: inset(0 3ch 0 0);
  animation: l4 1s steps(4) infinite;
}
</style>
