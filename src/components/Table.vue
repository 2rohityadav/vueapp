<template>
<div>
  <table class="table mt-1h">
    <thead class="thead-inverse">
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="user in users">
        <td>{{ user.name }}</td>
        <td>{{ user.email }}</td>
        <td>
          <button type="button"  @click="updateUser(user)">Edit</button>
        </td>
      </tr>
    </tbody>
  </table>

</div>
</template>
<script>
import { bus } from '../main'
export default {
  data() {
    return {
      users: [
        {name: 'jack', email: 'jack@jackass.com'},
        {name: 'marty', email: 'marty@madman.com'}
      ]
    }
  },
  // recieving bus event
  methods: {
    updateUser(user) {
      bus.$emit('e_updateuser', user)
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
