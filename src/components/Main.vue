<template>
  <div class="main">
      <div class="container">
        <div class="title-main">
            <h1>ORIGINALI NETFLIX</h1>
          </div>
        <div class="row">
          <Movies class="movies-container" v-for="movie in movies" :key="movie.id"
            :image="movie.poster_path"
            :title="movie.title"
            :originalTitle="movie.original_title"
            :originalLanguage="movie.original_language"
            :vote="movie.vote_average"
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
  color: white;
  background-color: black;
  height: calc(100vh - 50px);
}
</style>
