<template>
  <div class="movies-content">
      <div class="card-movie">
          <div class="info-movies">
            <div class="content-info">
                <div class="prova">{{title}}</div>
                <div class="prova">{{originalTitle}}</div>
                <div class="prova flag-container">
                    <img :src="getFlag(originalLanguage)" alt="">
                </div>
                <div class="prova">{{vote}}</div>
            </div>            
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
  }
}
</script>

<style lang="scss">
.movies-content{
    width: calc(100% / 6);
    padding: 5px;
    .card-movie{
        display: flex;
        height: 300px;
        background-image: url("https://image.tmdb.org/t/p/w342/hQq8xZe5uLjFzSBt4LanNP7SQjl.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        align-items: flex-end;
        justify-content: flex-end;
        .info-movies{
            height: 100%;
            width: 100%;
            background-color: rgba(5, 4, 4, 0.5);
            opacity: 0;
            display: flex;
            text-align: center;
            padding: 15px;
            &:hover{
                opacity: 1;
                font-size: 14px;
            }
            .flag-container{
                width: 50px;
                img{
                    width: 100%;
                }
            }
            .prova{
                align-self: center;
            }
        }
    }
}
</style>
