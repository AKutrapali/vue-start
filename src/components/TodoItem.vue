<template>
  <li>
    <span v-bind:class="{done:todo.completed}">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed">
      <strong>
        {{index + 1}}
      </strong>
      {{todo.title}}
    </span>
    
    <button v-on:click="$emit('remove-todo',todo.id)" >
      &times;
    </button>
  </li>
</template>

<script>

export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: Number
  },
  
}
</script>

<style>
li {
  border: 2px solid green;
  display: flex;
  justify-content: space-around;
  margin: 20px;
  padding: 20px;
}
button {
  background: crimson;
  border-radius: 50px;
  color: burlywood;
}
.done {
  text-decoration: line-through;
}
</style>
