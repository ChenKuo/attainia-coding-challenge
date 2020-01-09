<template>
  <div id="app">
    <div id="nav">
      <router-link to="/page1">Page1</router-link>
      <router-link to="/page2">Page2</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  created(){
    import('@/assets/users.json')
    .then(users => {
      this.$store.state.users = users.default
    })
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding-left: 1rem;
  padding-right: 1rem;
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  text-decoration: none;
  background-color:#cfc
}

#nav a.router-link-exact-active {
  background-color: #42b983;
  color: white;
}
</style>
