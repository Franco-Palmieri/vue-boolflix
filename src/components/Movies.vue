<template>
  <div class="movies-content">
      <div>{{title}}</div>
  </div>
</template>

<script>

export default {
  name: 'Movies',
  props: {
      title: String,
  },
  methods: {

  }
}
</script>

<style lang="scss">
.movies-content{
    border: 1px solid red;
}
</style>
