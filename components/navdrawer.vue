<template>
  <v-navigation-drawer
    class="nav-drawer"
    color="#242849"
    width="300"
    app
    absolute
    permanent
    left
    dark
  >
    <v-list-item class="px-8 py-6">
      <v-toolbar-title class="d-flex align-center">
        <img
          class="logo-img"
          src="~/static/img/brand-logo.svg"
          width="160"
          alt="..."
        />
      </v-toolbar-title>
    </v-list-item>

    <v-list dense>
      <v-list-item
        class="px-9 py-3 d-flex align-end"
        v-for="nav in navigations"
        :key="nav.title"
        :to="`${nav.link}`"
        v-ripple="false"
        link
      >
        <v-list-item-icon>
          <img class="icons" :src="nav.icon" width="20px" alt="..." />
        </v-list-item-icon>

        <v-list-item-content class="ml-n5 pa-0">
          <v-list-item-title class="text-body-1 font-weight-thin">{{
            nav.title
          }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      navigations: [
        { title: 'Dashboard', icon: 'dashboard-icon.svg', link: 'dashboard' },
        { title: 'Admin', icon: 'admin-icon.svg', link: 'admin' },
        { title: 'Players', icon: 'players-icon.svg', link: '/' },
        { title: 'Songs', icon: 'songs-icon.svg', link: 'songs' },
        { title: 'Artists', icon: 'artists-icon.svg', link: 'artists' },
        { title: 'Countries', icon: 'countries-icon.svg', link: 'countries' },
        {
          title: 'Leaderboard',
          icon: 'leaderboard-icon.svg',
          link: 'leaderboard',
        },
      ],
    }
  },
}
</script>
