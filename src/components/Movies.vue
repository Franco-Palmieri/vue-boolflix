<template>
  <div class="movies-content">
      <div class="picture">
          <img :src="image" alt="" width="100%">
      </div>
      <div class="info-movies">
            <div>{{title}}</div>
            <div>{{originalTitle}}</div>
            <div>{{originalLanguage}}</div>
            <div>1</div>
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
    border: 1px solid red;
    width: calc(100% / 3);
    .picture{
        img{
            width: 100%;
        }
    }
}
</style>
