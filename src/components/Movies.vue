<template>
  <div class="movies-content">
      <div class="card-movie">
          <div class="info-movies">
            <div class="prova">{{title}}</div>
            <div>{{originalTitle}}</div>
            <div>{{originalLanguage}}</div>
            <div>1</div>
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
        align-items: center;
        .info-movies{
            padding: 10px;
            background-color: rgba(5, 4, 4, 0.7);
            &:hover{
                color: yellow;
            }
        }
    }
}
</style>
