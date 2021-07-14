<template>
    <div>{{albums.genre}} </div>
    
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