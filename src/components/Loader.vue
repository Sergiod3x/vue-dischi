<template>
    <div class="loader">Loading...</div>
</template>

<script>
export default{
   name : "Loader" 
}
</script>

<style lang="scss" scoped>
    .loader{
        left: 0;
        position: fixed;
        width: 100%;
        height: 100vh;
        background: white;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>