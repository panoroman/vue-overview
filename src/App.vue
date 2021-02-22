<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <ToDo/>
  <!-- <input v-model="msg">
  {{msg}} -->
  <AddTodo
    @addTask='addToTasksList'
  />
  <ul>
    <li v-for="t in tasksList" :key="t.id">
      {{t.task}}
    </li>
  </ul>
  <!-- {{tasksList}} -->
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
      msg:'',
      tasksList: []
    }
  },
  methods: {
    addToTasksList(task) {
      this.tasksList.push(task)
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
