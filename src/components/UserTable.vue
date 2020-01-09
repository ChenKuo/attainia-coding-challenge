<template>
    <table>
      <thead>
      <tr>
        <th>id</th>
        <th>username</th>
        <th>last_login</th>
        <th>login_count</th>
        <th>project_count</th>
      </tr>
      </thead>
      <tbody>
        <UserRow v-for="user in users" :user="user" :colorFunc="colorFunc" :key="user.id"/>
      </tbody>
    </table>
</template>

<script>
import UserRow from '@/components/UserRow.vue'

export default {
  name: 'usertable',
  props:{
    users: Array,
    colorFunc: Function
  },
  components: {
    UserRow
  }
}
</script>

<style scoped>
table{
  border-spacing: 0;
  width: 100%;
}
thead{
    background-color: #ddd;
}
th{
    border: 1px solid #aaa;
}
</style>
