<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
    </div>
    <router-view :users="users"/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: []
    }
  },
  async created () {
    this.users = await this.fetchUsers()
  },
  methods: {
    async fetchUsers () {
      return await fetch('https://jsonplaceholder.typicode.com/users').then(response => response.json())
    }
  }
}
</script>