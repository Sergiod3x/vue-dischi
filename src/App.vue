<template>
  <div id="app">
    <Loader v-if="!(albums.success)"/>
    <button @click="searchAlbum(filteredArray)">Filtra</button>
    <Nav  @search="searchAlbum"/>
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
      this.filteredArray = result.data.response
    })
  },
  methods:{
    salutami(mex){
      alert(mex); 
    },
    searchAlbum(albumString){
      this.filteredArray = this.albums.response.filter((element)=>{
        // console.log("stringa"+albumString);
        // console.log(element);
        // console.log("anno" +element.year);
        // console.log("return" +element.year.includes("albumString"));
        if ((element.year.includes(albumString))||(element.genre.includes(albumString))||(element.author.includes(albumString))||(element.title.includes(albumString))){
          return true
        }
        false
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
