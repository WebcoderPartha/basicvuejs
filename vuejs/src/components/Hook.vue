<template>
  <div>
    <h2>Hooking</h2>
    <h3>Name : {{name}}</h3>
    <button class="btn btn-sm btn-info" @click="update()">Update Name</button>
  </div>
</template>

<script>
export default {
  name: "Hook",
  data(){
    return {
      name: 1
    }
  },
  beforeCreate() {
    alert('Before Created')
  },
  created() {
    alert('created')
  },
  beforeUpdate() {
    alert('Before update')
  },
  updated() {
    alert('Updated')
  },
  methods: {
    update(){
      this.name = 'tumpa';
    }
  }

}
</script>

<style scoped>

</style>