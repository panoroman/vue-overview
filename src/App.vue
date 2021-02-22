<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <ToDo/>
  <input v-model="msg">
  {{msg}}
  <AddTodo/>
</template>

<script>
import ToDo from './components/ToDo'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  components: {
    ToDo,
    AddTodo
  },
  data() {
    return {
      msg:''
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
