<template>
  <li>
    <!-- <div>{{ task.name }} {{ index }}</div> -->
    <div><slot></slot> {{ index }}</div>
    <small>{{ task.dueDate }} @ {{ task.dueTime }}</small>
    <button @click="deleteTask(index)">X</button>
  </li>
</template>
<script>
  import { defineComponent } from '@vue/composition-api'

  export default defineComponent({
    props: ['task', 'index'],
    setup() {

    },
  })
</script>
<style scoped>

</style>
