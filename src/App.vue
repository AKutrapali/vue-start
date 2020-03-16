<template>
  <div id="app">
    <AddTodo
    v-on:add-todo="addTodo"
    />
    <TodoList
    v-bind:todos= "todos"
    v-on:remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import AddTodo from './components/AddTodo'
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
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=10')
    .then(response => response.json())
    .then(json => {
      this.todos = json
    })
  },
  methods: {
    removeTodo: function (id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo: function (newObj) {
      this.todos.push(newObj)
    }
  },
  components: {
    TodoList,
    AddTodo
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
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}
</style>
