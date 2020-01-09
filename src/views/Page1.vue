<template>
  <div class="page1">
    <UserTable :users="users" :colorFunc="showZeroLogin?colorFunc:null"/>
    <button @click="this.toggleZeroLogin">toggle</button>
  </div>
</template>

<script>
import UserTable from '@/components/UserTable.vue'

export default {
  name: 'page1',
  components: {
    UserTable
  },
  data(){
    return {
      showZeroLogin: false
    }
  },
  computed: {
    users(){
      return this.$store.state.users
    }
  },
  methods: {
    toggleZeroLogin(){
      this.showZeroLogin = !this.showZeroLogin
    },
    colorFunc(user){
      if(this.showZeroLogin && user.login_count == 0){
        return '#f44'
      }
      return 'white'
    }
  }
}
</script>

<style scoped>
button{
  margin: 1rem;
}
</style>
