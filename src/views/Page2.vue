<template>
  <div class="page2">
    <UserTable :users="users" :colorFunc="colorRow?colorFunc:null"/>
    <button @click="this.toggle" :class="{'green-button':colorRow}">toggle</button>
  </div>
</template>

<script>
import UserTable from '@/components/UserTable.vue'

export default {
  name: 'page2',
  components: {
    UserTable
  },
  data(){
    return {
      colorRow: false
    }
  },
  computed: {
    users(){
      return this.$store.state.users
    }
  },
  methods: {
    toggle(){
      this.colorRow = !this.colorRow
    },
    // maps user to row color
    // this function is passed as prop to table component when using custom row coloring 
    colorFunc(user){
      if(user.login_count > 1){
        return '#4f4'
      }
      return 'white'
    }
  }
}
</script>

<style scoped>
button{
  padding: 0;
  border: none;
  outline: none;
  color: white;
  border-radius: 0.5rem;
  font-size: 1rem;
  width: 6rem;
  height: 2rem;
  margin: 1rem;
}
button{
  background-color: #66f;
}
button:hover{
  background-color:#44d;
}
button:active{
  background-color:#22a;
}
.green-button{
  background-color: #4b4;
}
.green-button:hover{
  background-color:#292;
}
.green-button:active{
  background-color:#070;
}
</style>
