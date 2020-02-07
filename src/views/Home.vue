<template>
  <div class="home">
    <h1>List of Users</h1>
    <div>Filter: <input v-model="name" type="text" placeholder="Insert name here"/></div>
    <ul v-for="(user, index) in users" :key="index">
      <router-link :to="`/users/${user.id}`">
       <li v-if="showUser(user.name)">{{ user.name }}</li>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: ''
    }
  },
  props: {
    users: {
      type: Array
    }
  },
  methods: {
    showUser (name) {
      return name.toLowerCase().includes(this.name)
    },
    sortUsersByName () {
      this.users.sort((a, b) => {
        if (a.name > b.name)
          return 1
        else if (a.name < b.name)
          return -1
        return 0
      })
    }
  },
  mounted () {
    this.sortUsersByName()
  }
}
</script>