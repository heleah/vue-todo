<template>
  <div id="app">
    <ToDos v-bind:todoEntries="todoEntries" />
  </div>
</template>

<script>
import ToDos from './components/ToDos.vue'

export default {
  name: 'App',
  components: {
    ToDos
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
  }
}
</script>

<style></style>
