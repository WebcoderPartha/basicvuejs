<template>
  <div>
    <h2>Online  Friend</h2>
    <table class="table table-stripe">
      <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Online</th>
      </tr>
      </thead>

      <tbody>
      <tr v-for="(fnd,index) in online" :key="index">
        <td v-if="fnd.online">{{ fnd.name }}</td>
        <td v-if="fnd.online">{{ fnd.email }}</td>
        <td v-if="fnd.online">{{ fnd.online }}</td>
      </tr>
      </tbody>

    </table>
  </div>
</template>

<script>
export default {
  name: "Online",
  props: ['online']
}
</script>

<style scoped>

</style>