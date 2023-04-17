<template>

  <div class="container">
    <h2>{{ title}}</h2>
    <Friends :friends="friends" />
    <Online :online="friends" />


  </div>

</template>

<script>

import Friends from "@/components/Friends";
import Online from "@/components/Online";
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
    Online
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
