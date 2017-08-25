<template>
<div class="hello">

  <h1>{{msg}}</h1>

  <div>
    <add-user></add-user>
  <div>
    <appTable></appTable>
  </div>

  </div>

</div>
</template>

<script>
import AddUser from './AddUser'
import Table from './Table'

export default {
  components: {
    'addUser': AddUser,
    'appTable': Table
  },
  name: 'hello',
  data() {
    return {
      msg: 'Vuejs'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  
</style>
