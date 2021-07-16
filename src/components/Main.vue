<template>
  <div class="main">
      <div class="container">
        <div class="row">
          <Movies class="movies-container" v-for="movie in movies" :key="movie.id"
          :title="album.title"
          :original_title="movie.orginal_title"
          :original_language="movie.original_language"
          :vote_average="movie.vote_average"
          />
        </div>
      </div>
  </div>
</template>

<script>
import Movies from "./Movies.vue"
export default {
  name: 'Main',
  components: {
    Movies,
  },
  props: {
    movies: Array,
  },
  methods: {
  }
}
</script>

<style lang="scss">
.main{
  background-color: lightgrey;
  height: calc(100vh - 50px);
}
</style>
