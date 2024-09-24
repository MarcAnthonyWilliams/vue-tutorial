<template>
  <div id="app">
    @{{ user.username }} - {{ fullName }}
    <strong> Followers: </strong> {{ followers }}
    <!-- V-on click ties the function made to the interaction with the button.-->
    <button v-on:click="followerUser"> Follow </button> 
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      followers: 0,
      user:{
        id: 1,
        username: '_MarcLikesLocs',
        firstName: 'MarcAnthony',
        lastname: 'Williams',
        email: 'mw4725@nyu.edu',
        isAdmin: true,
      }
    }
  },
  computed: {
    fullName(){
      return `${this.user.firstName} ${this.user.lastname}` 
    }
  },
  methods: {
    followerUser(){
      this.followers++
    }

  },
  mounted() {
    this.followerUser();
  }

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
