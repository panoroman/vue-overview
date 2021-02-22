<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <ToDo/>
  <!-- <input v-model="msg">
  {{msg}} -->
  <AddTodo
    @addTask='addToTasksList'
  />
  <ul>
    <li v-for="(t, index) in tasksList" :key="t.id" :class="{complete: t.completed}">
      <input type="checkbox" v-model="t.completed">
      {{t.task}}
      <button v-on:click="removeFromList(index)">&times;</button>
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
    },
    removeFromList(index) {
      this.tasksList.splice(index, 1)
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
ul {
  display: table;
  margin: auto;
  margin-top: 20px;
  min-width: 20%;
  list-style: none;
}

li {
  border: 1px solid;
  border-radius: 3px;
  display: flex;
  justify-content: space-between;
  margin-bottom: 15px;
  padding: 10px;
}

.complete {
  text-decoration: line-through;
}
</style>
