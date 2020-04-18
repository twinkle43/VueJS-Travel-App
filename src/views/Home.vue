<template>
  <div class="home">
    <h1>All destinations</h1>
    <div class="destinations">
      <div v-for="destination in destinations" v-bind:key="destination.name">   
        <router-link v-bind:to="{name:'DestinationDetails',params: {slug:destination.slug}}">
          <h2>{{destination.name}}</h2>
        </router-link>

        <figure> 
          <router-link v-bind:to="{name:'DestinationDetails',params:{slug:destination.slug}}"> 
            <img v-bind:src="require(`@/assets/${destination.image}`)"  v-bind:alt="destination.name"> 
          </router-link>
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
import store from "@/store.js";

export default {
  name: "Home",
  components: {},
  data() {
    return {
      destinations: store.destinations
    };
  }
};
</script>
<style scoped>
  .home{
    max-width: 1400px;
    margin : 0 auto;
  }

  img{
    max-width: 200px;
  }

.destinations{
  display: flex;
  justify-content:space-around;
}
</style>