<template>
  <div id="app">
    <Header @search="searchMovie"/>
    <Main :movies="moviesFiltered"/>
  </div>
</template>

<script>
import axios from "axios"
import Header from "./components/Header.vue"
import Main from "./components/Main.vue"


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data (){
    return {
      movies: [],
      moviesFiltered: [],
    }
  },
  created (){
    axios.get("https://api.themoviedb.org/3/search/movie?api_key=3cd005812fa42de2c7826b6521d70f3f&query=ritorno+al+futuro").then((results) =>{
      this.movies = results.data.results;
      this.moviesFiltered = results.data.results
    })
  },
  computed: {
  },
  methods: {
    searchMovie (){
      this.moviesFiltered = this.movies.filter((element) => {
        return this.element.title.includes(searchString);
      })
    }

  }
}
</script>

<style lang="scss">
@import "./style/app.scss"
</style>
