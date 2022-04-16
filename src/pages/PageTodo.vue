<template>
  <q-page padding>
    <q-list separator bordered class="q-pa-md">
      <q-item-label header>General</q-item-label>

      <q-item clickable tag="label" v-ripple v-for="task in tasks" :key="task.id" @click="task.completed = ! task.completed" :class="!task.completed ? bg-orange-1: bg-green1">
        <q-item-section side top>
          <q-checkbox v-model="task.completed" />
        </q-item-section>

        <q-item-section>
          <q-item-label :class="{'text-strikethrough' : task.completed}">{{ task.name }}</q-item-label>
          <q-item-label caption>
            {{ task.description }}
          </q-item-label>
        </q-item-section>
        <!-- <q-item-section side top> -->
        <q-item-section side>
          <div class="row">
            <div class="column justify-center" >
              <q-icon name="event" size="18px" class="q-mr-xs"/>
            </div>
            <div class="column">
              <q-item-label class="row justify-end" caption> {{ task.dueDate }} </q-item-label>
              <q-item-label class="row justify-end" caption> <small>{{ task.dueTime }}</small> </q-item-label>
            </div>
          </div>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'PageTodo',
    data () {
      return {
          tasks: [
            {
              id: 1,
              name: 'Go To Shop',
              completed: false,
              description: "Any text can be put here",
              dueDate: '2022/04/15',
              dueTime: '08:00'
            },
            {
              id: 2,
              name: 'get Bananas',
              completed: true,
              description: "Go get your bananas",
              dueDate: '2022/04/20',
              dueTime: '15:00'
            },{
              id: 3,
              name: 'get Apples',
              completed: false,
              description: "Make that as soon as possible",
              dueDate: '2022/04/25',
              dueTime: '20:00'
            }
          ]
      }
    },
    computed: {

    },
    methods: {

    },
    directives: {

    },
  })
</script>
<style scoped>

</style>>
