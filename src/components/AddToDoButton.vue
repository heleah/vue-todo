<template>
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title" />
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'

export default {
  name: 'AddToDoButton',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addToDo(e) {
      e.preventDefault()

      const newToDoObj = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }

      this.$emit('add-todo-event', newToDoObj)
      this.title = ''
    }
  }
}
</script>
