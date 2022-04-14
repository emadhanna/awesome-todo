<template>
  <q-page padding>
    <ul>
      <!-- <li v-for="(item, index) in tasks" :key="index">
        <div>{{ item.name }} {{ index }}</div>
        <small>{{ item.dueDate }} @ {{ item.dueTime }}</small>
        <button @click="deleteTask(index)">X</button>
      </li> -->
      <!-- <task v-for="(task, index) in tasks" :key="index" :task="task" :index="index"></task> -->
      <task v-for="(task, index) in tasks" :key="index" :task="task" :index="index">{{ task.name }}</task>
    </ul>
  </q-page>
</template>

<script>
  import Task from 'components/Task.vue'
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'IndexPage',
    data () {
      return {
        tasks: [
          {
            name: 'Go To Shop',
            dueDate: '2019/05/12',
            dueTime: '18:30'
          },
          {
            name: 'Get Bananas',
            dueDate: '2019/05/13',
            dueTime: '14:00'
          },
          {
            name: 'get Apples',
            dueDate: '2019/05/14',
            dueTime: '16:00'
          },
        ]
      }
    },
    computed: {

    },
    methods: {
      deleteTask(index) {
        this.tasks.splice(index, 1)
       }
    },
    components: {
      task: Task
      // 'task': require('components/Task.vue').default
    },
    directives: {

    }
  })
</script>
<style scoped>

</style>>
