<template>
  <div>
    <h2>All Friend</h2>
    <table class="table table-stripe">
      <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Online</th>
        <th>Action</th>
      </tr>
      </thead>

      <tbody>
      <tr v-for="(fnd,index) in friends" :key="index">
        <td>{{ fnd.name }}</td>
        <td>{{ fnd.email }}</td>
        <td>{{ fnd.online }}</td>
        <td><button @click="unfriend(fnd.name)" class="btn btn-sm btn-danger">Delete</button></td>
      </tr>
      </tbody>

    </table>
  </div>
</template>

<script>
export default {
  name: "Friends",
  props: [
      'friends'
  ],
  methods:{
    unfriend(name){
      this.$emit('delete', {name});
    }
  }
}
</script>

<style scoped>

</style>