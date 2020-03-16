<template>
  <ul >
    <TodoItem
    v-for="(todo, i) of todos" :key="todo.id"
    v-bind:todo= "todo"
    v-bind:index="i"
    v-on:remove-todo="removeTodo"
    />
  </ul>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  props: ['todos'],
  components: {
    TodoItem
    
  },
  methods: {
    removeTodo: function (id) {
      this.$emit('remove-todo',id)
    },
  }
}
</script>

<style scoped>
  ul {
    width: 500px;
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>
