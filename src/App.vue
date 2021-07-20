<template>
  <div id="app">
    <Header @search="searchAll($event)"/>
    <Main :movies="movies" :series="series" :popular="popular"/>
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
      movies: [],
      series : []
    }
  },
  created (){
    this.callApi();
  },
  computed: {
  },
  methods: {
    callApi(){
      axios.get("https://api.themoviedb.org/3/movie/popular?api_key=3cd005812fa42de2c7826b6521d70f3f").then((results) =>{
      this.popular = results.data.results;
      });
    },
    searchMulti (searchString){
      if (searchString.length == 0){
        return this.callApi()
      }
      axios.get(`https://api.themoviedb.org/3/search/multi?api_key=3cd005812fa42de2c7826b6521d70f3f&query=${searchString}`).then((results) =>{
      this.popular = results.data.results;
      console.log(this.popular)
      })
    },
    searchMovie (searchString){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=3cd005812fa42de2c7826b6521d70f3f&query=${searchString}`).then((result)=>{
        this.movies = result.data.results;
        console.log(searchString)
      })
    },
    searchSeries (searchString){
      console.log("ciao")
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=3cd005812fa42de2c7826b6521d70f3f&query=${searchString}`).then((result)=> {
        this.series = result.data.results;
        console.log(this.series)
      })
    },
    searchAll (searchString){
      this.searchMovie (searchString)
      this.searchSeries(searchString)
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss"
</style>
