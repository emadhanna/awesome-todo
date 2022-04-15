<template>
  <!-- <q-route-tab :to="link" :icon="icon" :label=changeToUppercase(title) /> -->
  <q-route-tab :to="link" :icon="icon" :label=changeToUppercase(title) />
</template>

<script>
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'RouteTabs',
    props: {
      title: {
        type: String,
        required: true
      },

      caption: {
        type: String,
        default: ''
      },

      link: {
        type: String,
        default: '#'
      },

      icon: {
        type: String,
        default: ''
      }
    },
    methods: {
      changeToUppercase (item){
        return item.toUpperCase()
      }
    }
  })
</script>

<style scoped>

</style>
