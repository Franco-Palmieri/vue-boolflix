<template>
  <div class="movies-content">
      <div class="image-container">
          <img :src="completeImage(image)" alt="">
      </div>
      <div class="info-movie">
          <div class="info-content">
                <div class="title">{{title}}</div>
                <div class="title">{{originalTitle}}</div>
                <div class="title flag-container">
                    <img :src="getFlag(originalLanguage)" alt="">
                </div>
                <div class="title">{{vote}}</div>
          </div>
        
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
    display: flex;
    align-items: center;
    img{
        width: 100%;
    }
    .info-movie{
        height: calc(100% - 10px);
        width: calc(100% - 10px);
        background-color: rgba(5, 4, 4, 0.5);
        opacity: 0;
        position: absolute;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
        &:hover{
            opacity: 1;
        }
        .flag-container{
            img{
                max-width: 50px;
            }
        }
        .title{
            width: 100%;
            margin: 0;
        }
    }
}
</style>
