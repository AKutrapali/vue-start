<template>
  <form v-on:submit.prevent="onSubmit">
    <input type="text" v-model="title">
    <button type="submit">
      Create
    </button>
  </form>
</template>

<script>

export default {
  data() {
    return {
      title:''
    }
  },
  props: {
   
  },
  methods: {
    onSubmit() {
      console.log(this.title)
      const newObj = {
        id: Date.now(),
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', newObj)
      this.title = ''
    }
  }
  
}
</script>

<style>
  form {
    width: 400px;
  }
</style>
