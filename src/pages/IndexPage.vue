<template>
  <q-page class="flex flex-center" padding>
    <!-- <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    > -->
    <!-- <h5>I love Vue.js</h5> -->
    <!-- <h5>I love Vue.JS!</h5> -->
    <q-card class="my-card" style="width: 600px">
      <q-card-section>
        <div class="text-h4">
          T0-Do List
        </div>
      </q-card-section>
      <q-card-section>
        <div class="row justify-center">
          <div class="col-12 q-pd-md">
            <q-input v-model="todoTask" label="Input Task">
            <template v-slot:after>
              <q-btn round dense flat icon="send" @click="addItem" />
            </template>
            </q-input>
          </div>
        </div>
      </q-card-section>

      <q-separator />

      <q-card-section v-if="todoList.length > 0">
        <div class="row justify-center" v-for="(item, index) in todoList" :key="index">
          <div class="col-8 q-py-md">
            {{ item.value }}
          </div>
          <div class="col-auto q-py-md">
            <q-btn round dense flat icon="done" @click="removeItem(index)" />
          </div>
        </div>
      </q-card-section>
      <q-card-section v-else>
        <div class="row justify-center">
          <div class="col-auto">
            <div class="text-h6">
              {{ noItemsFound }}
            </div>
          </div>
        </div>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'IndexPage',
    data () {
      return {
        todoTask: '',
        noItemsFound: 'No Items Found',
        todoList: [
          { value: "Create An App"},
          { value: "Build An App"}
        ]
      }
    },
    methods: {
      addItem () {
        this.todoList.push( { value: this.todoTask} )
      },
      removeItem(index){
        this.todoList.splice( index, 1 )
      }
    }
  })
</script>
<style scoped>

</style>>
