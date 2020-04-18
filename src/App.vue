<template>
  <div id="app">
    <Navigation />
    <router-view v-bind:key="$route.path" />
  </div>
</template>

<script>
  import Navigation from "@/components/Navigation.vue"

  export default {
    components :{
      Navigation
    }
  }
</script>


<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  a:-webkit-any-link {
    color: black;
    cursor: pointer;
    text-decoration: none;
  }

  a:hover{
    text-decoration: underline;
  }
</style>
