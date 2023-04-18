<template>
  <div>
    <h2>Posts</h2>
    <div class="form-group">
      <label for="Search">Seach Post</label>
      <input type="text" class="form-control" id="Search" v-model="post_search" placeholder="Seach post">
    </div>
    <table class="table table-stripe">
      <thead>
        <tr>
          <th>UserId</th>
          <th>Title</th>
          <th>Body</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(post,index) in searchPost" :key="index+1">
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
      posts: [],
      post_search: ''
    }
  },
  computed: {
    searchPost(){
      return this.posts.filter(post => {
        if (post.title.match(this.post_search) || post.body.match(this.post_search)){
          return post.title.match(this.post_search)
        }
      });
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
  },

}
</script>

<style scoped>

</style>