<template>
  <div id="app">
    <Loader v-if="!(albums.success)"/>
    <button @click="searchAlbum(filteredArray)">Saluta</button>
    <Nav  @search="serchAlbum"/>
    <Main :albums="filteredArray"/>

  </div>
</template>

<script>
import axios from "axios";
import Nav from "./components/Nav.vue";
import Main from "./components/Main.vue";
import Loader from "./components/Loader.vue";

export default {
  name: 'App',
  components: {
    Nav,
    Main,
    Loader,
  },
  data(){
    return{
      albums:{},
      filteredArray:[]
    }
  },
  created(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((result)=> {
      this.albums = result.data
      this.filteredArray = result.data
    })
  },
  methods:{
    salutami(mex){
      alert(mex); 
    },
    searchAlbum(albumString){
      this.filteredArray = this.albums.response.filter((element)=>{
        return element.title.includes("albumString");
      })

       

    }
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
