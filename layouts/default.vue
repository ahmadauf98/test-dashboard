<template>
  <v-app>
    <!-- Navigation Drawer -->
    <NavDrawer />

    <!-- Body Content -->
    <v-main class="bg-color">
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
import navdrawer from '../components/navdrawer'

export default {
  components: {
    NavDrawer: navdrawer,
  },

  data() {
    return {}
  },
}
</script>
