<template>
    <div>
        <Album v-for="(albums, index) in albums" :key="index"
         :albums="albums" />
    </div>
    
    
</template>

<script>
import Album from "./Album.vue";
export default{
   name : "Main", 
   components: {
       Album
   },
   props : {
       albums : Array
   }
}
</script>

<style lang="scss" scoped>

</style>