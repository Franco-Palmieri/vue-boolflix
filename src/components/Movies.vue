<template>
  <div class="movies-content">
      <div class="image">
          <img :src="image" alt="">
      </div>
      <div>{{title}}</div>
      <div>{{originalTitle}}</div>
      <div>{{originalLanguage}}</div>
      <div>1</div>
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
}
</style>
