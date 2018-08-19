<template>
  <div id="app">
    <h1>My TodoList App!</h1>
    <todoList/>
  </div>
</template>

<script>
import todoList from './components/todoList.vue'

export default {
  components: {
    todoList
  }  
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 400px;
  margin: 0 auto;
  margin-top: 60px;
}

h1, h2 {
  text-align: center;
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}
</style>
