<template>

  <div class="container">
    <h2>{{ title}}</h2>
    <Friends :friends="friends" @delete="destroy" />
    <Online :online="friends" />
    <Hook />


  </div>

</template>

<script>

import Friends from "@/components/Friends";
import Online from "@/components/Online";
import Hook from "@/components/Hook";
export default {
  name: 'App',
  data(){
    return {
      title: 'Welcome to Bangladesh',
      friends: [
        {name: 'Partha', email: 'Psarth@gmail.com', online: true},
        {name: 'Sohel', email: 'sohel@gmail.com', online: false},
        {name: 'Tumpa', email: 'tumpa@gmail.com', online: true},
        {name: 'Mitu', email: 'mitu@gmail.com', online: true},
      ]
    }
  },
  components: {
    Friends,
    Online,
    Hook
  },
  methods: {
    destroy(payload){
      this.friends = this.friends.filter(friend => {
        return friend.name !== payload.name;
      })
    }
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
  margin-top: 60px;
}
</style>
