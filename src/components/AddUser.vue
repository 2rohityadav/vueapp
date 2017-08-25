<template>
<div>
  <br>
  <!-- form input to add content -->
  <form>
    <div>
      <div>
        <input type="text" placeholder="Name" v-model="newUsers.name">
      </div>
    </div>

    <div>
      <div>
        <input type="email" placeholder="Email" v-model="newUsers.email">
      </div>
    </div>
    <button type="button"  @click="save()">Save</button>
</form>
<!-- -->

</div>
</template>

<script>
import { bus } from '../main'
export default {
  data() {
    return {
      newUsers: {
        name: '',
        email: ''
      }
    }
  },
  created() {
    //do something after creating vue instance
    bus.$on('e_updateuser', (user) => {
      console.log(user);
      this.newUsers.name = user.name;
      this.newUsers.email= user.email;
    })
  },
  methods: {
    save(user) {
      console.log('save users: '+user);
      // help me how do save updated data into the list
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
