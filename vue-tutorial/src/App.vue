<template>
  <div id="app">
   <UserProfile/> 
  </div>
</template>

<script>
import UserProfile from './components/UserProfile.vue';
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {UserProfile}
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  text-align: center;

}
</style>
