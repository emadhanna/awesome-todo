<template>
  <!-- <q-page class="flex flex-center" padding> -->
  <q-page padding>
    <button style="position: absolute; right: 10px" @click="counter++">{{ counter }}</button>
    <!-- <input v-model="message" @keyup="handleKeyUp"/> -->
    <!-- <input v-model="message" @keyup.esc="handleKeyUp" @keyup.enter="alertMessage" @mouseenter="alertMessage"/> -->
    <!-- <input v-model="message" @keyup.esc="handleKeyUp" @keyup.enter="alertMessage" @mouseleave="alertMessage"/> -->
    <!-- <input v-model="message" @keyup.esc="handleKeyUp" @keyup.enter="alertMessage" v-autofocus v-bind:class="{ 'error': message.length > 22}"/> -->
    <input v-model="message" @keyup.esc="handleKeyUp" @keyup.enter="alertMessage" v-autofocus :style="errorStyle" ref="messageInput" />
    <!-- <button @click="message= ''">Clear Message</button> -->
    <button @click="clearMessage">Clear Message</button>
    <div>{{ message.length }}</div>
    <!-- <h5 class="border-grey" v-show="message.length">{{ message }}</h5> -->
    <h5 class="border-grey" v-if="message.length">{{ message }}</h5>
    <h6 v-else>No Message Entered</h6>

    <hr>

    <!-- <p>Uppercase Message: {{ messageUppercase() }}</p> -->
    <p>Uppercase Message: {{ messageUppercase }}</p>
    <!-- <p>Lowercase Message: {{ message | messageLowercase }}</p> -->
    <p>Lowercase Message: {{ messageLowercase }}</p>
  </q-page>
</template>

<script>
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'IndexPage',
    data () {
      return {
        message: 'I love Vue.Js Coding!',
        counter: 0
      }
    },
    computed: {
      messageUppercase() {
        console.log('messageUpercase Was Fired')
        return this.message.toUpperCase() + this.counter
      },
      messageLowercase() {
        console.log('messageLowercase Was fired')
        return this.message.toLowerCase() + this.counter
      },
      errorStyle() {
        if (this.message.length > 22){
          return {
            'color': 'red',
            'background': 'pink'
          }
        }
      }
    },
    methods: {
      clearMessage () {
        this.message = ''
      },
      alertMessage (){
        alert(this.message)
      },
      handleKeyUp (e){
        console.log(e)
        if (e.keyCode == 27) {
          this.clearMessage()
        }
        else if (e.keyCode == 13){
          this.alertMessage()
        }
      }
    },
    directives: {
      autofocus: {
        inserted (element) {
          element.focus()
        }
      }
    },
    // beforeCreate() {
    //   console.log('beforeCreate!!!!')
    // },
    // beforeCreate() {
    //   console.log('created!!!!')
    // },
    // beforeMount() {
    //   console.log('beforeMount!!!!')
    // },
    mounted() {
      console.log('mounted!!!!')
      console.log(this.$refs)
      this.$refs.messageInput.className = 'bg-green'
    },
    // beforeUpdate() {
    //   console.log('beforeUpdate!!!!')
    // },
    // updated() {
    //   console.log('Updated!!!!')
    // },
    // beforeDestroy() {
    //   console.log('beforeDestroy!!!!')
    // },
    // destroyed() {
    //   console.log('destroyed!!!!')
    // }
  })
</script>
<style scoped>
  .border-grey {
    border: 1px solid grey;
  }

  input, button {
    font-size: 23px;
  }

  .error {
    color: red;
    background: pink;
  }
</style>>
