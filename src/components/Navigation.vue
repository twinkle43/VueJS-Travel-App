<template>
    <nav id="nav">
      <p class="logo"> The Vue School Travel App </p>
      <ul class="nav-links">
          <li class="links">  
              <router-link to="/"> Home </router-link>
          </li>

          <li v-for="destination in destinations" v-bind:key="destination.name" class="links"> 
              <router-link v-bind:to="{
                  name : 'DestinationDetails',
                  params : {slug:destination.slug}
              }"> 
                {{destination.name}}
              </router-link>
          </li>
      </ul>    
    </nav>
</template>

<script>
import store from "@/store.js";
export default {
    data(){
        return{
            destinations : store.destinations
        };
    }
}
</script>

<style scoped>
    #nav{
        display: flex;
        padding: 10px;     
        text-decoration: none;
    }

    .nav-links{
        display: flex;
    }

    .links {
      padding-right: 20px ;
      text-decoration: none;
      list-style: none;
    }

    .links:hover{
        text-decoration: underline;
    }

    #nav a.router-link-exact-active {
        color: #42b983;
    }

    .logo{
        font-size: 20px;
        color : #42b983;
        font-weight: bold;
    }
</style>