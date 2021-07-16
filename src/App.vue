<template>
  <div id="app">
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
    }
  },
  created (){
    axios.get("https://api.themoviedb.org/3/search/movie?api_key=3cd005812fa42de2c7826b6521d70f3f&query=ritorno+al+futuro").then((result) =>{
      this.movies = result.data.response;
    })
  },
  computed: {
  },
  methods: {

  }
}
</script>

<style lang="scss">
@import "./style/app.scss"
</style>
