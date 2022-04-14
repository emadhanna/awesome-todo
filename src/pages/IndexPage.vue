<template>
  <q-page class="flex flex-center" padding>
    <div class="inline-block">
      <div>
        <!-- <q-btn glossy icon="run_circle" color="primary" text-color="white" label="Click Me!" /> -->
        <!-- <q-btn glossy icon-right="run_circle" color="primary" text-color="white" label="Click Me!" /> -->
        <q-btn glossy icon="school" icon-right="run_circle" color="primary" text-color="white" label="Click Me!" />
      </div>
      <div class="q-py-md">
        <q-btn rounded glossy icon="mail" icon-right="danger" color="secondary" text-color="Black" label="Click Me!" :loading="isLoading" />
      </div>
      <div class="q-py-md">
        <q-btn rounded>
          <q-avatar size="50px">
            <img src="~assets/quasar-logo-vertical.svg" />
          </q-avatar>
        </q-btn>
      </div>
      <div class="q-py-md">
        <!-- <q-btn flat rounded color="orange" icon="mail" label="Click Me!"/> -->
        <!-- <q-btn flat round color="orange" icon="mail" /> -->
        <!-- <q-btn outline rounded color="orange" label="Click Me!" /> -->
        <q-btn :ripple="{ color: 'yellow' }" align="around" push rounded color="orange" label="Click Me!" />
      </div>
      <div  class="q-py-md">
        <q-btn-group rounded>
          <q-btn rounded label="Home" />
          <q-btn rounded label="People" />
          <q-btn rounded label="Message" />
        </q-btn-group>
      </div>
      <div class="q-pa-md">
        <q-btn-dropdown color="primary" label="Dropdown Button">
          <q-list>
            <q-item clickable v-close-popup @click="onItemClick('Photos')">
              <q-item-section>
                <q-item-label>Photos</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick('Videos')">
              <q-item-section>
                <q-item-label>Videos</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick('Arcticles')">
              <q-item-section>
                <q-item-label>Articles</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </div>
    </div>
  </q-page>
</template>

<script>
  import { defineComponent } from 'vue'

  export default defineComponent({
    name: 'IndexPage',
    data () {
      return {
       isLoading: true,
       useData: false,
       useWifi: false
      }
    },
    methods: {
      onItemClick (item) {
        console.log('You Have Clicked ' +  item + '!')
      }
    }
  })
</script>
<style scoped>

</style>>
