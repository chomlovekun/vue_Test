<template>
    <div>
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand" href="#">
    <img src="@/assets/logo.png" width="30" height="30" class="d-inline-block align-top" alt="">
    {{text}}
  </a>
</nav>
    </div>
</template>

<script>
    export default {
        props:{
            text :{
                type : String,
                default : "Hello World"
            } 
        }
    }
</script>

<style scoped>

</style>