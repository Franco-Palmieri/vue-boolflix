<template>
  <div class="main">
      <div class="container">
        <div class="row">
          <Movies class="movies-container" v-for="movie in albums" :key="movie.id"
          :title="album.title"
          :original_title="album.orginal_title"
          :original_language="album.original_language"
          :vote_average="album.vote_average"
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
    albums: Array,
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
