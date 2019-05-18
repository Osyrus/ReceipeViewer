<template>
  <v-app>
    <v-toolbar app>
      <!-- This is the button for the side nav menu drawer thing -->
      <v-toolbar-side-icon @click.stop="toggleDrawer" />

      <!-- This is the main toolbars title in the top left -->
      <v-toolbar-title class="headline text-uppercase">
        <span>Recipe</span>
        <span class="font-weight-light">Viewer</span>
      </v-toolbar-title>

      <v-spacer />
      <!-- Add any side stuff here to go to the top right -->
    </v-toolbar>

    <LeftDrawer
      v-model="leftDrawerOpen"
    />

    <v-content>
      <HelloWorld />
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import LeftDrawer from './components/LeftDrawer'

export default {
  name: 'App',
  components: {
    HelloWorld,
    LeftDrawer
  },
  data: () => ({
    leftDrawerOpen: false
  }),
  methods: {
    toggleDrawer () {
      if (this.leftDrawerOpen) {
        console.log('Close drawer')
        this.leftDrawerOpen = false
      } else {
        console.log('Open drawer')
        this.leftDrawerOpen = true
      }
    }
  }
}
</script>
