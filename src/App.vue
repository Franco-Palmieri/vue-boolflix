<template>
  <div id="app">
    <Header @search="searchMovie"/>
    <Main :movies="moviesFiltered" :series="series" @search="[searchMovie($event), searchSerie($event)]"/>
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
      popular: [],
      moviesFiltered: [],
      series : []
    }
  },
  created (){
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=3cd005812fa42de2c7826b6521d70f3f").then((results) =>{
      this.popular = results.data.results;
      this.moviesFiltered = results.data.results;
    });
  },
  computed: {
  },
  methods: {

    searchMovie (searchString){
      if (searchString.length == 0){
        this.moviesFiltered = this.popular
        return ;
      }
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=3cd005812fa42de2c7826b6521d70f3f&query=${searchString}`).then((results) =>{
      this.moviesFiltered = results.data.results;
      })
    },
    searchSeries (searchString){
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=3cd005812fa42de2c7826b6521d70f3f&query=${searchString}`).then((result)=> {
        this.series = result.data.results;
        console.log(result.data.results)
      })
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss"
</style>
