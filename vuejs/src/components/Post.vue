<template>
  <div>
    <h2>Posts</h2>
    <table class="table table-stripe">
      <thead>
        <tr>
          <th>UserId</th>
          <th>Title</th>
          <th>Body</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(post,index) in posts" :key="index+1">
          <td>{{ post.userId}}</td>
          <td>{{ post.title}}</td>
          <td>{{ post.body.substring(0,40)+".."}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "Post",
  data(){
    return {
      posts: []
    }
  },
  created() {
    this.getPost();
  },
  methods: {
    getPost(){
      axios.get('https://jsonplaceholder.typicode.com/posts')
          .then((response) =>{
            this.posts = response.data
          }).catch(error => {

      })
    }
  }
}
</script>

<style scoped>

</style>