<template>
  <div class="main">
      <div class="container">
        <div class="title-main">
            <h1>ORIGINALI NETFLIX</h1>
          </div>
          <div v-if="movies.length === 0 && series.length === 0">
            <div class="row movies-contenitore"> 
              <div class="title-section"><h2>Populars</h2></div>           
                <Movies class="movies-container" v-for="movie in popular" :key="movie.id"
                :image="movie.poster_path"
                :title="movie.title"
                :originalTitle="movie.original_title"
                :originalLanguage="movie.original_language"
                :vote="movie.vote_average"
              />
            </div>              
          </div>
          <div v-else>
            <div class="row movies-contenitore">   
              <div class="title-section"><h2>Film</h2></div>         
                <Movies class="movies-container" v-for="movie in movies" :key="movie.id"
                :image="movie.poster_path"
                :title="movie.title"
                :originalTitle="movie.original_title"
                :originalLanguage="movie.original_language"
                :vote="movie.vote_average"
                />
                <div class="title-section"><h2>Series</h2></div> 
                <Movies class="movies-container" v-for="movie in series" :key="movie.id"
                :image="movie.poster_path"
                :title="movie.title"
                :originalTitle="movie.original_title"
                :originalLanguage="movie.original_language"
                :vote="movie.vote_average"
                />
            </div>   
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
    popular: Array,
    series: Array
  },
  methods: {
  }
}
</script>

<style lang="scss">
.main{
  color: white;
  background-color: black;
  .movies-contenitore{
    display: flex;
    justify-content: flex-start;
    .title-section{
      width: 100%;
    }
  }
}
</style>
