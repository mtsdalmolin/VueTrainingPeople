<template>
    <div>
      <div>
        <h1>Name: {{ CurrentUser.name }}</h1>
        <h2>Username: {{ CurrentUser.username }}</h2>
        <h2>Email: {{ CurrentUser.email }}</h2>
      </div>
      <div>
        <h2>Street: {{ CurrentUser.address.street }}</h2>
        <h2>Suite: {{ CurrentUser.address.suite }}</h2>
        <h2>City: {{ CurrentUser.address.city }}</h2>
        <h2>Zipcode: {{ CurrentUser.address.zipcode }}</h2>
        <h2>Latitude: {{ CurrentUser.address.geo.lat }}</h2>
        <h2>Longitude: {{ CurrentUser.address.geo.lng }}</h2>
      </div>
      <div>
        <h2>Website: {{ CurrentUser.website }}</h2>
        <h2>Phone: {{ CurrentUser.phone }}</h2>
        <h2>Name: {{ CurrentUser.company.name }}</h2>
        <h2>Catchphrase: {{ CurrentUser.company.catchPhrase }}</h2>
        <h2>BS: {{ CurrentUser.company.bs }}</h2>
      </div>
    </div>
</template>

<script>
export default {
  props: {
    users: {
      type: Array
    }
  },
  computed: {
    CurrentUser() {
      return this.users.find(user => user.id === +this.$route.params.id)
    }
  }
}
</script>