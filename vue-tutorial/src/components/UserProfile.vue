<template>

    <div id="card">
        <div class="user-profile">
            <div class="user-profile_username"> @{{ user.username }} </div>
            <div class="user-profile_admin-badge" v-if="user.isAdmin">Admin</div>
            <div class="user-profile_admin-badge" v-else>Not Admin</div>
            <div class="user-profile_follower-count"><strong> Followers: </strong> {{ followers }} </div>
            <!-- V-on click ties the function made to the interaction with the button.-->
           <!-- <button v-on:click="followerUser"> Follow </button> -->
        </div>
        <div class="card_twoots-wrapper">
           <TwootItem v-for="twoot in user.twoots" :key="twoot.id" :username="user.username" :twoot="twoot"> </TwootItem>
        </div>
    </div>
  </template>
  
<script>
import TwootItem from './TwootItem.vue'

  export default {
    name: 'UserProfile',
    components: {TwootItem},
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
            twoots: [
                {id: 1, content: 'Twotter is amazing!'}, // twoot
                {id: 2, content: "Man I love Tems."}
            ]
        }
      }
    },
    watch: {
      followers(newFollowerCount, oldFollowerCount){
        if(oldFollowerCount < newFollowerCount){
          console.log(`${this.user.username} has gained a follower! `)
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
      //when component is rendered, run everything here.
      this.followerUser();
    }
  
  }
  
  </script>
  
  <style>
  #card{
    display: grid;
    grid-template-columns: 1fr 3fr;
    width: 100%;
    padding: 50px, 5%;
  }
  .user-profile {
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    display: flex;
    flex-direction: column;
    margin-right: 50px;
    padding: 15px 60px 20px 20px;
    background-color: white;
    border-radius: 4px;
    border: 1px solid #DFE3E8;
    box-shadow: 0px 2px 4px rgba(0,0,0,0.2);
    height: 7rem;
  }

  .user-profile_follower-count{
    text-align: left;
  }
  .user-profile_username{
    font-weight: bold;
    font-size: xx-large;
  }

  .user-profile_admin-badge{
    background: purple;
    color: white;
    border-radius: 5px;
    margin-right: auto ;
    padding: 0 10px;

  }
  </style>
  