<template>
  <div id="app">
    <TodoList
    v-bind:todos= "todos"
    />
  </div>
</template>

<script>
import TodoList from './components/TodoList'
export default {
  name: 'App',
  data () {
    return {
      todos: [
        { id: 0, title: 'Купить хлеб', completed: false },
        { id: 1, title: 'Купить пиво', completed: false },
        { id: 2, title: 'Купить виски', completed: false }
      ]
    }
  },
  components: {
    TodoList
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  justify-content: center;
}
</style>
