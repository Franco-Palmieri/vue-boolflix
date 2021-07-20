<template>
  <div class="movies-content">
      <div class="image-container">
          <img :src="completeImage(image)" alt="">
      </div>
      <div class="info-movie">
        <div class="title">{{title}}</div>
        <div class="original-title">{{originalTitle}}</div>
        <div class="title">{{original_language}}</div>
        <div class="title">{{vote}}</div>
      </div>
      
  </div>
</template>

<script>

export default {
  name: 'Movies',
  props: {
      title: String,
      originalTitle: String,
      originalLanguage: String,
      image: String,
      vote: Number
  },
  methods: {
      getFlag (originalLanguage){
          return require("../assets/flags/" + originalLanguage + ".png");
      },
      completeImage (image){
          return `http://image.tmdb.org/t/p/w500/${image}`;
      }
  }
}
</script>

<style lang="scss">
.movies-content{
    width: calc(100% / 6);
    padding: 5px;
    position: relative;
    img{
        width: 100%;
    }
    .info-movies{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
}
</style>
