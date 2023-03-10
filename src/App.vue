<template>
  <div id="app">
    <ToDos v-bind:todoEntries="todoEntries" @delete-todo-event="deleteToDoItem" />
    <AddToDoButton @add-todo-event="addToDoItem" />
  </div>
</template>

<script>
import AddToDoButton from './components/AddToDoButton.vue'
import ToDos from './components/ToDos.vue'

export default {
  name: 'App',
  components: {
    ToDos,
    AddToDoButton
  },
  data() {
    return {
      todoEntries: [
        {
          id: 1,
          title: 'Gather information',
          completed: false
        },
        {
          id: 2,
          title: 'Create test project',
          completed: false
        },
        {
          id: 3,
          title: 'Write blog entry',
          completed: false
        }
      ]
    }
  },
  methods: {
    addToDoItem(newToDoItem) {
      this.todoEntries = [...this.todoEntries, newToDoItem]
    },
    deleteToDoItem(toDoId) {
      this.todoEntries = this.todoEntries.filter((todo) => todo.id !== toDoId)
    }
  }
}
</script>

<style></style>
