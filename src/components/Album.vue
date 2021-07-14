<template>

    <div>{{albums.poster}} 
   {{albums.author}} 
   {{albums.genre}} 
   {{albums.year}} 
  </div>

    
</template>

<script>
export default{
   name : "Album", 
   props : {
       albums : Object
   }
}
</script>

<style lang="scss" scoped>

</style>