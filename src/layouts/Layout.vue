<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense round icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />
        <q-toolbar-title class="absolute-center"><strong style="color:yellow">Biography</strong></q-toolbar-title>
        <!-- <div>Quasar v{{ $q.version }}</div> -->
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered :breakpoint="700" :width="250" class="bg-primary">
      <q-list dark>
        <q-item-label header><strong>Navigation</strong></q-item-label>
        <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>
    <q-footer elevated>
       <!-- <q-toolbar>
         <q-toolbar-title>Footer</q-toolbar-title>
       </q-toolbar> -->
      <q-tabs inline-label class="bg-primary text-white shadow-2">
        <!-- <q-route-tab to="/" icon="list" label="TODO" />
        <q-route-tab to="/settings" icon="settings" label="SETTINGS" /> -->
        <RouteTabs v-for="link in essentialLinks" :key="link.title" v-bind="link" />
      </q-tabs>
    </q-footer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'
import RouteTabs from 'components/RouteTabs.vue'

const linksList = [
  {
    title: 'To Do',
    caption: 'Introductory Page',
    icon: 'fact_check',
    link: '/'
    // link: 'https://quasar.dev'
  },
  {
    title: 'Settings',
    caption: 'Settings Page',
    icon: 'settings',
    link: '/settings'
  },
  {
    title: 'About',
    caption: 'Info Page',
    icon: 'info',
    link: '/about'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
    RouteTabs
},

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>

<style lang=scss scoped>
  @media screen and (min-width: 700px){
    .q-footer {
      display: none
    }
  }
  .q-drawer {
      .q-router-link--exact-active{
      color: yellow !important
    }
  }
</style>
