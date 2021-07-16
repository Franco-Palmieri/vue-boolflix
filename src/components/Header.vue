<template>
  <div class="header">
      <div class="nav">
          <ul class="nav-list-left">
                <li>Logo</li>
                <li><a href="#">Home</a></li>
                <li><a href="#">Serie TV</a></li>
                <li><a href="#">Film</a></li>
                <li><a href="#">Originali</a></li>
                <li><a href="#">Aggiunti di recente</a></li>
                <li><a href="#">La mia lista</a></li>
            </ul>
            <ul class="nav-list-rigth">
                <li><input type="text" placeholder="search" v-model="searchString"></li>
                <li><a href="#">BAMBINI</a></li>
                <li>Notifiche</li>
                <li>Altro</li>
            </ul>    
      </div>
  </div>
</template>

<script>

export default {
  name: 'Header',
  data() {
   return{
       searchString: "",
   }   
  },
  methods: {

  }
}
</script>

<style lang="scss">
.header{
    .nav{
        height: 50px;
        background-color: black;
        display: flex;
        justify-content: space-between;
        color: lightgrey;
        .nav-list-left{
            display: flex;
            list-style: none;
            li{
                margin: 0 5px;
                a{
                    color: lightgrey;
                    text-decoration: none;
                    &:hover{
                        color: white;
                    }
                }
            }
        }
        .nav-list-rigth{
            display: flex;
            list-style: none;
            margin: 0 5px;
            li{
                margin: 0 5px;
                    a{
                        color: lightgrey;
                        text-decoration: none;
                        &:hover{
                        color: white;
                    }
                }
            }
        }
    }
}
</style>
