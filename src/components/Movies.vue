<template>
  <div class="movies-content">
      <div class="card-movie">
          <div class="info-movies">
            <div class="content-info">
                <div class="prova">{{title}}</div>
                <div class="prova">{{originalTitle}}</div>
                <div class="prova">{{originalLanguage}}</div>
                <div class="prova">1</div>
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
      image: String
  },
  methods: {

  }
}
</script>

<style lang="scss">
.movies-content{
    width: calc(100% / 3);
    padding: 5px;
    .card-movie{
        display: flex;
        height: 600px;
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
            align-items: center;
            &:hover{
                opacity: 1;
            }
            .prova{
                align-self: center;
            }
        }
    }
}
</style>
