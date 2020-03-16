<template>
  <li>
    <span>
      <input type="checkbox">
      <strong>
        {{todo.id}}
      </strong>
      {{todo.title}}
    </span>
    
    <button>
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
    }
  },
  components: {

  }

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
