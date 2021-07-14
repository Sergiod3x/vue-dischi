<template>
  <div id="app">
    <Nav />
    <Main :albums="albums.response"/>

  </div>
</template>

<script>
import axios from "axios";
import Nav from "./components/Nav.vue";
import Main from "./components/Main.vue";

export default {
  name: 'App',
  components: {
    Nav,
    Main,
  },
  data(){
    return{
      albums:{}
    }
  },
  created(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((result)=> {
      this.albums = result.data
    })
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
