<template>
  <v-navigation-drawer
    v-model="drawerOpen"
    absolute
    temporary
  >
    <v-toolbar flat>
      <v-list>
        <v-list-tile>
          <v-list-tile-title class="title">
            The side menu
          </v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-toolbar>

    <v-divider />

    <v-list
      dense
      class="pt-0"
    >
      <v-list-tile>
        <v-list-tile-action>
          <v-icon>mdi-account</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
          <v-list-tile-title>
            Account
          </v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: 'LeftDrawer',
  props: {
    value: Boolean
  },
  data: () => ({
    drawerOpen: false
  }),
  watch: {
    value: function (newOpen) {
      this.drawerOpen = newOpen
    },
    drawerOpen: function (newOpen) {
      if (this.value && !newOpen) {
        this.$emit('input', false)
      }
    }
  }
}
</script>

<style scoped>

</style>
