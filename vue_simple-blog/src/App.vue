<template>
  <!-- <div id="app">
    <img src="./assets/logo.png"> 
    <router-view/>
  </div> -->
  <div id="wrapper">
    <index/>
    
  </div>
</template>

<script>
  import hello from './components/HelloWorld'
  import index from './components/index'
  export default {
    name: 'App',
    components:{
      index:index,
    }
  }
</script>

<style>

</style>
