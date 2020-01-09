<template>
  <div class="page1">
    <UserTable :users="users" :colorFunc="colorRow?colorFunc:null"/>
    <button @click="this.toggle" :class="{'red-button':colorRow}">toggle</button>
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
      if(user.login_count === 0){
        return '#f44'
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
.red-button{
  background-color: #f66;
}
.red-button:hover{
  background-color:#d44;
}
.red-button:active{
  background-color:#a22;
}
</style>
