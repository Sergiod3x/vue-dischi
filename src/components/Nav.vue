<template>
    <div>
    
       <input type="text" placeholder="Search" v-model="searchString"
       @keyup.enter="$emit('search', searchString)"/>
       
    </div>
</template>

<script>
export default{
   name : "Nav",
   data() {
       return{
           searchString : ""
       }

   }
}
</script>

<style lang="scss" scoped>

</style>