<template>
    <tr :style="{backgroundColor:color}">
        <td>{{user.id}}</td>
        <td>{{user.username}}</td>
        <td>{{user.last_login}}</td>
        <td>{{user.login_count}}</td>
        <td>{{user.project_count}}</td>
    </tr>
</template>

<script>
export default {
  name: 'user_row',
  props: {
    user: Object,
    colorFunc: Function
  },
  computed: {
    color(){
    
      return (this.colorFunc||this.defaultColorFunc)(this.user)
    }
  },
  methods: {
      defaultColorFunc(){
          return 'white'
      }
  }
}
</script>

<style scoped>
td,th{
  border: 1px solid #ccc;
}

</style>
